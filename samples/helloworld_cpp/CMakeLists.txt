cmake_minimum_required(VERSION 3.2)
project(helloworld_cpp CXX)
include("${WUT_ROOT}/share/wut.cmake" REQUIRED)

add_executable(helloworld_cpp
   main.cpp)

target_link_libraries(helloworld_cpp
   whb
   coreinit
   proc_ui
   sysapp
   nn_ac)

wut_default_malloc(helloworld_cpp)
wut_enable_newlib(helloworld_cpp)
wut_enable_stdcpp(helloworld_cpp)

wut_create_rpx(helloworld_cpp.rpx
               helloworld_cpp)

install(FILES "${CMAKE_CURRENT_BINARY_DIR}/helloworld_cpp.rpx"
        DESTINATION "${CMAKE_INSTALL_PREFIX}")
