vtk_module_third_party(JsonCpp
  VERSION 0.7.0)
if (WIN32 AND VTK_USE_SYSTEM_JSONCPP)
  option(VTK_SYSTEM_JSONCPP_SHARED "System-installed JsonCpp package is a shared library" OFF)
  mark_as_advanced(VTK_SYSTEM_JSONCPP_SHARED)
endif()

configure_file(
  "${CMAKE_CURRENT_SOURCE_DIR}/vtk_jsoncpp_fwd.h.in"
  "${CMAKE_CURRENT_BINARY_DIR}/vtk_jsoncpp_fwd.h")
if (NOT VTK_INSTALL_NO_DEVELOPMENT)
  install(
    FILES       "${CMAKE_CURRENT_BINARY_DIR}/vtk_jsoncpp_fwd.h"
    DESTINATION "${VTK_INSTALL_INCLUDE_DIR}/vtk_jsoncpp"
    COMPONENT   Development)
endif ()
