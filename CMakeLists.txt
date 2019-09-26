cmake_minimum_required(VERSION 3.8)

project(qvisualisation)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)


ADD_DEFINITIONS (${QT_DEFINITIONS})


# find_package (Qt5 REQUIRED COMPONENTS Widgets Core Gui Network printsupport svg webenginecore webengine webenginewidgets webview webchannel Qml)


SET(QT5_MODULES Widgets Core Gui Network PrintSupport svg webenginecore webengine webenginewidgets webview webchannel Qml)

find_package (Qt5 REQUIRED COMPONENTS ${QT5_MODULES})






INCLUDE_DIRECTORIES(".\\GeneratedFiles")


         
add_executable(qvisualisation
    mainwindow.ui
    mainwindow.cpp
    main.cpp
    core/visualisationdatamodel.cpp 
    core/visualisationviewmodel.cpp 
    core/visualisationviewwidget.cpp 
    core/scatterplotviewwidget.cpp 
    core/matrixscatterplotviewwidget.cpp 
    core/parallelcoordinatesplotviewwidget.cpp 
    core/visualisationdatamodel.h 
    core/visualisationviewmodel.h 
    core/visualisationviewwidget.h 
    core/scatterplotviewwidget.h 
    core/matrixscatterplotviewwidget.h 
    core/parallelcoordinatesplotviewwidget.h 
    mainwindow.h    
    visualisation.qrc
)	 

       
       
       
target_link_libraries( qvisualisation Qt5::WebEngineWidgets)



target_link_libraries( qvisualisation Qt5::PrintSupport)

       
       
       

set_target_properties(${PROJECT_NAME} PROPERTIES
	CXX_STANDARD 17
	CXX_STANDARTD_REQUIRED ON
)


qt5_use_modules(qvisualisation Widgets Core Gui Network printsupport svg webenginecore webengine webenginewidgets webchannel webview Qml)
