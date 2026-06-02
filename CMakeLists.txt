cmake_minimum_required(VERSION 3.20)

project(libnkutils LANGUAGES C)

file(GLOB src src/*.c)

add_library(${PROJECT_NAME} ${src})

target_compile_definitions(${PROJECT_NAME} PRIVATE NK_EXPORT= )
target_compile_definitions(${PROJECT_NAME} PRIVATE SYSCONFDIR="/usr/local/etc")
target_link_libraries(${PROJECT_NAME} PUBLIC ${GLIB_LIBRARIES})
target_include_directories(${PROJECT_NAME} PUBLIC ${GLIB_INCLUDE_DIRS})
target_link_directories(${PROJECT_NAME} PUBLIC ${GLIB_LIBRARY_DIRS})
target_include_directories(${PROJECT_NAME} PUBLIC include)