cmake_minimum_required(VERSION 2.8)
project(cmake-options)

macro(SET_OPTION option value)
  set(${option} ${value} CACHE "" INTERNAL FORCE)
endmacro()

# Let's override the values
SET_OPTION(WITH_FEATURE_AA  OFF)
SET_OPTION(WITH_FEATURE_BB  ON)

# Join the project_A directory
add_subdirectory(project_A)