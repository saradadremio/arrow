# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.

if (PARQUET_BUILD_EXAMPLES)
  add_executable(parquet-reader-writer reader-writer.cc)
  add_executable(parquet-reader-writer2 reader-writer2.cc)
  target_include_directories(parquet-reader-writer PRIVATE .)
  target_include_directories(parquet-reader-writer2 PRIVATE .)
  target_link_libraries(parquet-reader-writer parquet_static)
  target_link_libraries(parquet-reader-writer2 parquet_static)

  add_dependencies(parquet
    parquet-reader-writer
    parquet-reader-writer2)
endif()
