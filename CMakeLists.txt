cmake_minimum_required (VERSION 2.6)
project(quasimontecarlo)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")

find_package(GSL REQUIRED)
include_directories(${GSL_INCLUDE_DIRS})
set(LIBS ${LIBS} ${GSL_LIBRARIES})

set(LIBS ${LIBS} m)

add_library(quasimontecarlo quasimontecarlo.c)

add_executable(qmc_test quasimontecarlo.c test.c)
target_link_libraries(qmc_test ${LIBS})
