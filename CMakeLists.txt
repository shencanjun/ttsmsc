cmake_minimum_required(VERSION 3.2)
PROJECT(ttsmsc)

include_directories(${PROJECT_NAME} include 3rd/include)

link_directories(/home/ros/work/ttsmsc/3rd/libs/x64)

add_library(${PROJECT_NAME} SHARED src/ttsmsc.cpp)

target_link_libraries(${PROJECT_NAME} 
                      msc_tts)

#INSTALL(TARGETS ${PROJECT_NAME} DESTINATION lib)

#INSTALL(FILES ${INH} DESTINATION include)

## 安装目标文件
INSTALL(TARGETS ${PROJECT_NAME}
        EXPORT ${PROJECT_NAME}
        LIBRARY DESTINATION lib
        INCLUDES DESTINATION include)

## 安装头文件
INSTALL(DIRECTORY ${PROJECT_SOURCE_DIR}/include/ ${PROJECT_SOURCE_DIR}/3rd/include DESTINATION include/)
