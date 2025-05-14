cmake_minimum_required(VERSION 3.14)
project(livox_sdk2)

set(livox_sdk2_MAJOR_VERSION 0)
set(livox_sdk2_MINOR_VERSION 0)
set(livox_sdk2_PATCH_VERSION 0)
set(livox_sdk2_VERSION
  ${livox_sdk2_MAJOR_VERSION}.${livox_sdk2_MINOR_VERSION}.${livox_sdk2_PATCH_VERSION})

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()


if (CMAKE_CROSSCOMPILING)
	set(THREADS_PTHREAD_ARG
		"PLEASE_FILL_OUT-FAILED_TO_RUN"
		CACHE STRING "Result from TRY_RUN" FORCE)
endif()

if (UNIX)
	set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")
endif(UNIX)

add_subdirectory(sdk_core)
# add_subdirectory(samples)

# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
