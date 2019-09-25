cmake_minimum_required(VERSION 3.8)

project(qvisualisation)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)


ADD_DEFINITIONS (${QT_DEFINITIONS})


find_package (Qt5 REQUIRED COMPONENTS Widgets Core Gui Network printsupport svg webenginewidgets webchannel)


INCLUDE_DIRECTORIES(".\\GeneratedFiles")

set(SRCS main.cpp
         mainwindow.cpp)
         
	 

         
add_executable(${PROJECT_NAME} ${SRCS})

set_target_properties(${PROJECT_NAME} PROPERTIES
	CXX_STANDARD 17
	CXX_STANDARTD_REQUIRED ON
)


qt5_use_modules(qvisualisation Widgets Core Gui Network printsupport svg webenginewidgets webchannel)
