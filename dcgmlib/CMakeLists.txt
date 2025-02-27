# Copyright (c) 2021, NVIDIA CORPORATION.  All rights reserved.
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
add_library(dcgm_interface INTERFACE)

target_include_directories(dcgm_interface INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/src
    ${CMAKE_CURRENT_BINARY_DIR}
    )
target_link_libraries(dcgm_interface INTERFACE sdk_nvml_interface)

install(FILES
        dcgm_agent.h
        dcgm_structs.h
        dcgm_fields.h
        dcgm_errors.h
        dcgm_api_export.h
    DESTINATION
        ${DCGM_INCLUDE_INSTALL_PREFIX}
    COMPONENT DCGM
)
