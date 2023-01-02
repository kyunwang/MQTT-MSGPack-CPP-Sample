cmake_minimum_required(VERSION 3.10)

project(MainExec)

add_executable(mainExec main.cpp)

set_property(TARGET mainExec PROPERTY CXX_STANDARD 17)

target_include_directories(mainExec PUBLIC ../libs/paho.mqtt.cpp/src)
target_include_directories(mainExec PUBLIC ../libs/json/include)

target_link_libraries(mainExec PUBLIC paho-mqttpp3 nlohmann_json)
