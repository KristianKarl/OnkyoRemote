project(OnkyoRemote)
cmake_minimum_required(VERSION 2.6)
find_package(Qt4 REQUIRED)

FILE(GLOB_RECURSE SOURCE_FILES src/*.cpp)
FILE(GLOB_RECURSE MOC_HDR_FILES src/*.h)

include_directories(${QT_INCLUDES} ${CMAKE_CURRENT_BINARY_DIR})

QT4_WRAP_CPP( MOC_SOURCE_FILES ${MOC_HDR_FILES} )

QT4_ADD_RESOURCES(ONKYOREMOTE_RCC_SRCS src/OnkyoRemote.qrc)

add_executable(OnkyoRemote ${SOURCE_FILES} ${MOC_SOURCE_FILES} ${ONKYOREMOTE_RCC_SRCS})
target_link_libraries(OnkyoRemote ${QT_QTCORE_LIBRARY} ${QT_QTGUI_LIBRARY} ${QT_QTNETWORK_LIBRARY})
install( TARGETS OnkyoRemote DESTINATION bin )