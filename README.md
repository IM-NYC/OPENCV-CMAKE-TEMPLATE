# OPENCV-CMAKE
A ultimate CMakeLists.txt for people who struggles compiling C/C++ code using the OpenCV library.

### *Only tested on macOS, please email me if it works for windows too

# Installation

1. First, install [HomeBrew](https://brew.sh).

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

2. Then after HomeBrew is installed, install the opencv package.

`brew install opencv`

3. Git clone this repository.

`git clone https://github.com/IM-NYC/OPENCV-CMAKE.git`

4. Git clone the [OpenCV](https://github.com/opencv/opencv) repository into a dependencies folder.

`mkdir dependencies & cd dependencies & git clone https://github.com/opencv/opencv.git`

5. Create a build folder inside the OpenCV repository, cmake and make it.

`cd opencv & mkdir build & cd build & cmake .. & make`

6. After all of that, head into the CMakeLists.txt file in the OPENCV-CMAKE repository and change the source directory (`add_executable(${PROJECT_NAME} src/main.cpp)`)

7. Head to the OPENCV-CMAKE repository and create a build directory so we can complie our code.

`mkdir build & cd build & cmake .. & make`

<br>
<img src="https://img.shields.io/badge/VSCode-0078D4?style=for-the-badge&logo=visual%20studio%20code&logoColor=white"/> <img src="https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white"/> <img src="https://img.shields.io/badge/OpenCV-27338e?style=for-the-badge&logo=OpenCV&logoColor=white"/> <img src="https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white"/> <img src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white"/>
<img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FIM-NYC1212%2Fhit-counter"/>
