# ----------------------------------------------------------------------------
#  CMake file for python support
# ----------------------------------------------------------------------------

if((WIN32 AND CMAKE_BUILD_TYPE STREQUAL "Debug")
    OR (BUILD_opencv_world AND NOT ENABLE_IOS_PYTHON)
    )
  ocv_module_disable(python2)
  ocv_module_disable(python3)
endif()

if((ANDROID OR APPLE_FRAMEWORK OR WINRT) AND NOT ENABLE_IOS_PYTHON)
  ocv_module_disable(python2)
  ocv_module_disable(python3)
endif()

add_subdirectory(python2)
add_subdirectory(python3)
