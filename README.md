## OpenCV: Open Source Computer Vision Library

### Resources

* Homepage: <https://opencv.org>
  * Courses: <https://opencv.org/courses>
* Docs: <https://docs.opencv.org/4.x/>
* Q&A forum: <https://forum.opencv.org>
  * previous forum (read only): <http://answers.opencv.org>
* Issue tracking: <https://github.com/opencv/opencv/issues>
* Additional OpenCV functionality: <https://github.com/opencv/opencv_contrib> 


### Contributing

Please read the [contribution guidelines](https://github.com/opencv/opencv/wiki/How_to_contribute) before starting work on a pull request.

#### Summary of the guidelines:

* One pull request per issue;
* Choose the right base branch;
* Include tests and documentation;
* Clean up "oops" commits before submitting;
* Follow the [coding style guide](https://github.com/opencv/opencv/wiki/Coding_Style_Guide).

### Linux build library

#### download source code

git colne https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git

#### build

cd opencv
mkdir build && cd build

 ********************* start 这是一条命令*********************
 
cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D WITH_CUDA=OFF \
-D WITH_IPP=OFF \
-D OPENCV_EXTRA_MODULES_PATH=`pwd`/../../opencv_contrib/modules \
-D BUILD_opencv_python3=ON \
-D BUILD_opencv_python2=OFF \
-D PYTHON3_EXECUTABLE=/usr/bin/python3 \
-D PYTHON3_INCLUDE_DIR=/usr/include/python3.10 \
-D PYTHON_DEFAULT_EXECUTABLE=/usr/bin/python3 \
-D PYTHON3_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython3.10.so.1.0 \
-D BUILD_opencv_hdf=OFF \
-D BUILD_EXAMPLES=OFF ..

 ********************* end 这是一条命令*********************

** 解析：

OPENCV_EXTRA_MODULES_PATH 为 https://github.com/opencv/opencv_contrib.git 源码路径

PYTHON3_EXECUTABLE 为python环境路径或系统python路径，可通过whereis python 查找

PYTHON3_INCLUDE_DIR 为python头文件环境路径或系统python头文件路径

PYTHON3_LIBRARY 为python 库路径

make && sudo make install

sudo ldconfig
