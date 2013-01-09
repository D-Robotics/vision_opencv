# add library
add_library(${PROJECT_NAME} cv_bridge.cpp)
add_dependencies(${PROJECT_NAME} sensor_msgs_gencpp)
target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS} ${catkin_LIBRARIES})

install(TARGETS ${PROJECT_NAME}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)

# add a Boost Python library
set(Python_ADDITIONAL_VERSIONS 2.7)
find_package(PythonLibs REQUIRED)

include_directories(SYSTEM ${PYTHON_INCLUDE_PATH}
                           ${Boost_INCLUDE_DIRS}
)

add_library(${PROJECT_NAME}_boost module.cpp)
target_link_libraries(${PROJECT_NAME}_boost ${Boost_LIBRARIES}
                                            ${catkin_LIBRARIES}
                                            ${PROJECT_NAME}
)

set_target_properties(${PROJECT_NAME}_boost PROPERTIES
                      LIBRARY_OUTPUT_DIRECTORY ${CATKIN_BUILD_PREFIX}/${CATKIN_GLOBAL_PYTHON_DESTINATION}/${PROJECT_NAME}/boost/
                      PREFIX ""
)
