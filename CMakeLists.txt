cmake_minimum_required(VERSION 3.10)

project(MSGPack_MQTT
	LANGUAGES CXX
)

set(PAHO_BUILD_STATIC TRUE)
add_subdirectory(libs/paho.mqtt.c)

set(PAHO_MQTT_C_INCLUDE_DIRS ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/libs/paho.mqtt.c/src)
add_subdirectory(libs/paho.mqtt.cpp)
add_subdirectory(libs/json)

# Build and keeps context of the libs
add_subdirectory(src)