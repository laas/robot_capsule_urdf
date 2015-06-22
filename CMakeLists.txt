# Copyright (C) 2011 CNRS
#
# Author: Florent Lamiraux
#
# This program is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program.  If not, see <http://www.gnu.org/licenses/>.

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

SET(PROJECT_NAME robot_capsule_urdf)
SET(PROJECT_DESCRIPTION
  "Generation of capsule collision models urdf files."
  )
SET(PROJECT_URL https://github.com/laas/robot_capsule_urdf)
SET(CUSTOM_HEADER_DIR ${PROJECT_NAME})

INCLUDE(cmake/base.cmake)
INCLUDE(cmake/cpack.cmake)

# Where to compile shared objects
SET(LIBRARY_OUTPUT_PATH ${PROJECT_BINARY_DIR}/lib)

SETUP_PROJECT()
ADD_REQUIRED_DEPENDENCY(urdfdom >= 0.2.9)
INSTALL(PROGRAMS
  bin/robot_capsule_urdf
  DESTINATION ${CMAKE_INSTALL_PKGLIBDIR}
  )

INSTALL(PROGRAMS
  package.xml
  DESTINATION ${CMAKE_INSTALL_DATAROOTDIR}
  )

SETUP_PROJECT_FINALIZE()
