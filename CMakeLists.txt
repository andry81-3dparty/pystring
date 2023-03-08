cmake_minimum_required(VERSION 3.0)

include(tacklelib/Project)

project("pystring")

set(PROJECT_LIB_NAME pystring)

tkl_check_var(REQUIRED PATH   PYSTRING_BRANCH_NAME) # ex: `1_1_3_20200204`

set(PROJECT_EXTERNALS_DIR "_externals")
set(PYSTRING_EXTERNAL_SOURCE_DIR "${CMAKE_CURRENT_LIST_DIR}/${PROJECT_EXTERNALS_DIR}/${PYSTRING_BRANCH_NAME}")


file(GLOB_RECURSE all_headers ${PYSTRING_EXTERNAL_SOURCE_DIR}/pystring.h*)
file(GLOB_RECURSE all_sources ${PYSTRING_EXTERNAL_SOURCE_DIR}/pystring.c*)

add_library(${PROJECT_LIB_NAME} STATIC ${all_headers};${all_sources})

tkl_initialize_library_target_defaults(${PROJECT_LIB_NAME} "anybit")

tkl_source_groups_from_dir_list("Header Files" FILES ${PYSTRING_EXTERNAL_SOURCE_DIR} *.h*)
tkl_source_groups_from_dir_list("Source Files" FILES ${PYSTRING_EXTERNAL_SOURCE_DIR} *.c*)

if(GCC)
  tkl_add_target_compile_properties(${PROJECT_LIB_NAME} *
    -Wall -Wextra -Wshadow -Wconversion -Wcast-qual -Wformat=2
  )
endif()
