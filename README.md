English| [简体中文](./README_cn.md)

ros2 vision_opencv contains packages to interface ROS 2 with [OpenCV](http://opencv.org/), which is a library designed for computational efficiency and strong focus on real-time computer vision applications. This repository contains:
* `cv_bridge`: Bridge between ROS 2 image messages and OpenCV image representation
* `image_geometry`: Collection of methods for dealing with image and pixel geometry
* `opencv_tests`: Integration tests to use the capabilities of the packages with OpenCV
* `vision_opencv`: Meta-package to install both `cv_bridge` and `image_geometry`

To use ROS 2 with OpenCV, please refer to the details within the [cv_bridge](https://github.com/ros-perception/vision_opencv/tree/ros2/cv_bridge) package.