cmake_minimum_required (VERSION 3.3)
project (rbox-iou)

find_package (Boost 1.68 REQUIRED)
include_directories(${Boost_INCLUDE_DIR})

SET( Boost_INCLUDE_DIR "/usr/local/include/boost" )
IF( NOT Boost_INCLUDE_DIR )
    MESSAGE( FATAL_ERROR "Please point the environment variable Boost_INCLUDE_DIR to the include directory of your Boost installation.")
ENDIF()
INCLUDE_DIRECTORIES ( "${Boost_INCLUDE_DIR}" )

add_subdirectory(pybind11)
pybind11_add_module(rbox-iou box_ops.cc)
