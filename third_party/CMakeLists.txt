# Copyright 2019 IBM Corporation
# 
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
# 
#     http://www.apache.org/licenses/LICENSE-2.0
# 
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

cmake_minimum_required (VERSION 2.8)

# only build gtest when it is checked out (if CMakeLists.txt is present, we
# assume this is the case)
if(EXISTS "${PROJECT_SOURCE_DIR}/third_party/googletest/CMakeLists.txt")
    # EXCLUDE_FROM_ALL only causes targets to be built only when needed as an dependency.
    # Also install targets are not installed (we do not want gtest to be installed)
    add_subdirectory(googletest EXCLUDE_FROM_ALL)
endif()

add_subdirectory(gRPC_utils)
