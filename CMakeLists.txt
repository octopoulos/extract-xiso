cmake_minimum_required(VERSION 3.0)
project(extract-xiso)

set (CMAKE_CXX_STANDARD 20)

string(TOUPPER __${CMAKE_SYSTEM_NAME}__ TARGET_OS)

find_package(fmt CONFIG REQUIRED)

set(SOURCE_FILES
	extract-xiso.cpp
)

add_executable(extract-xiso ${SOURCE_FILES})
target_compile_definitions(extract-xiso PRIVATE ${TARGET_OS})

target_link_libraries(extract-xiso PRIVATE fmt::fmt-header-only)

# ${INSTALL_PREFIX}
install(TARGETS extract-xiso RUNTIME DESTINATION "c:/utils/bin")
