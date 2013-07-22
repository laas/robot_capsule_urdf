CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

SET(PROJECT_NAME robot_capsule_urdf)
SET(PROJECT_DESCRIPTION
  "Generation of capsule collision models urdf files."
  )
SET(PROJECT_URL https://github.com/laas/robot_capsule_urdf)
SET(CUSTOM_HEADER_DIR ${PROJECT_NAME})

INCLUDE(cmake/base.cmake)
INCLUDE(cmake/cpack.cmake)
INCLUDE(cmake/catkin.cmake)

# Where to compile shared objects
SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)

SETUP_PROJECT()
ADD_REQUIRED_DEPENDENCY(urdf_parser_py >= 0.3)
INSTALL(PROGRAMS
  bin/robot_capsule_urdf
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
  )
SETUP_PROJECT_FINALIZE()
