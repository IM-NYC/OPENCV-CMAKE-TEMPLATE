cmake_minimum_required(VERSION 3.31.3)
project(program VERSION 0.0.0)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED True)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)


#C FLAGS
set(CMAKE_C_FLAGS_INIT                "-Wall -std=c11")
set(CMAKE_C_FLAGS_DEBUG_INIT          "-g")
set(CMAKE_C_FLAGS_MINSIZEREL_INIT     "-Os -DNDEBUG")
set(CMAKE_C_FLAGS_RELEASE_INIT        "-O3 -DNDEBUG")
set(CMAKE_C_FLAGS_RELWITHDEBINFO_INIT "-O2 -g")


#C++ FLAGS
set(CMAKE_CXX_FLAGS_INIT                "-Wall -std=c++17")
set(CMAKE_CXX_FLAGS_DEBUG_INIT          "-g")
set(CMAKE_CXX_FLAGS_MINSIZEREL_INIT     "-Os -DNDEBUG")
set(CMAKE_CXX_FLAGS_RELEASE_INIT        "-O3 -DNDEBUG")
set(CMAKE_CXX_FLAGS_RELWITHDEBINFO_INIT "-O2 -g")


#EXECUTABLE FILE LOCATION
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY bin)


# DIR TO SOURCE FILES
add_executable(${PROJECT_NAME} src/main.cpp)

#(-l) DYLIB DIRS
# OPENCV BINARY LIBRARIES
if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_calib3d.4.10.0.dylib)
find_library(libopencv_calib3d.4.10.0 OpenCV_calib3d)
else()
message(FATAL_ERROR "Couldn't find the libopencv_calib3d.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_core.4.10.0.dylib)
find_library(libopencv_core.4.10.0 OpenCV_core)
else()
message(FATAL_ERROR "Couldn't find the libopencv_core.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_dnn.4.10.0.dylib)
find_library(libopencv_dnn.4.10.0 OpenCV_dnn)
else()
message(FATAL_ERROR "Couldn't find the libopencv_dnn.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_features2d.4.10.0.dylib)
find_library(libopencv_features2d.4.10.0 OpenCV_features2d)
else()
message(FATAL_ERROR "Couldn't find the libopencv_features2d.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_flann.4.10.0.dylib)
find_library(libopencv_flann.4.10.0 OpenCV_flann)
else()
message(FATAL_ERROR "Couldn't find the libopencv_flann.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_gapi.4.10.0.dylib)
find_library(libopencv_gapi.4.10.0 OpenCV_gapi)
else()
message(FATAL_ERROR "Couldn't find the libopencv_gapi.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_highgui.4.10.0.dylib)
find_library(libopencv_highgui.4.10.0 OpenCV_highgui)
else()
message(FATAL_ERROR "Couldn't find the libopencv_highgui.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_imgcodecs.4.10.0.dylib)
find_library(libopencv_imgcodecs.4.10.0 OpenCV_imgcodecs)
else()
message(FATAL_ERROR "Couldn't find the libopencv_imgcodecs.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_imgproc.4.10.0.dylib)
find_library(libopencv_imgproc.4.10.0 OpenCV_imgproc)
else()
message(FATAL_ERROR "Couldn't find the libopencv_imgproc.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_ml.4.10.0.dylib)
find_library(libopencv_ml.4.10.0 OpenCV_ml)
else()
message(FATAL_ERROR "Couldn't find the libopencv_ml.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_objdetect.4.10.0.dylib)
find_library(libopencv_objdetect.4.10.0 OpenCV_objdetect)
else()
message(FATAL_ERROR "Couldn't find the libopencv_objdetect.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_photo.4.10.0.dylib)
find_library(libopencv_photo.4.10.0 OpenCV_photo)
else()
message(FATAL_ERROR "Couldn't find the libopencv_photo.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_stitching.4.10.0.dylib)
find_library(libopencv_stitching.4.10.0 OpenCV_stitching)
else()
message(FATAL_ERROR "Couldn't find the libopencv_stitching.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_video.4.10.0.dylib)
find_library(libopencv_video.4.10.0 OpenCV_video)
else()
message(FATAL_ERROR "Couldn't find the libopencv_video.4.10.0 binary lib.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build/lib/libopencv_videoio.4.10.0.dylib)
find_library(libopencv_videoio.4.10.0 OpenCV_videoio)
else()
message(FATAL_ERROR "Couldn't find the libopencv_videoio.4.10.0 binary lib.")
endif()


#(-I) INCLUDE DIRS TO DEPENDENCIES
# OPENCV INCLUDE DIRS
if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/include)
else()
message(FATAL_ERROR "Couldn't find opencv include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/build)
else()
message(FATAL_ERROR "Couldn't find opencv_modules include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/core/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/core/include)
else()
message(FATAL_ERROR "Couldn't find core include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/calib3d/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/calib3d/include)
else()
message(FATAL_ERROR "Couldn't find calib3d include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/dnn/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/dnn/include)
else()
message(FATAL_ERROR "Couldn't find dnn include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/features2d/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/features2d/include)
else()
message(FATAL_ERROR "Couldn't find features2d include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/flann/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/flann/include)
else()
message(FATAL_ERROR "Couldn't find flann include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/gapi/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/gapi/include)
else()
message(FATAL_ERROR "Couldn't find gapi include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/highgui/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/highgui/include)
else()
message(FATAL_ERROR "Couldn't find highgui include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/imgcodecs/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/imgcodecs/include)
else()
message(FATAL_ERROR "Couldn't find imgcodecs include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/imgproc/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/imgproc/include)
else()
message(FATAL_ERROR "Couldn't find imgproc include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/ml/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/ml/include)
else()
message(FATAL_ERROR "Couldn't find ml include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/objdetect/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/objdetect/include)
else()
message(FATAL_ERROR "Couldn't find objdetect include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/photo/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/photo/include)
else()
message(FATAL_ERROR "Couldn't find photo include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/stitching/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/stitching/include)
else()
message(FATAL_ERROR "Couldn't find stitching include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/ts/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/ts/include)
else()
message(FATAL_ERROR "Couldn't find ts include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/video/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/video/include)
else()
message(FATAL_ERROR "Couldn't find video include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/videoio/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/videoio/include)
else()
message(FATAL_ERROR "Couldn't find videoio include directory.")
endif()

if (EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/world/include)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/dependencies/opencv/modules/world/include)
else()
message(FATAL_ERROR "Couldn't find world include directory.")
endif()


#(-L) DYLIB NAMES
# OPENCV DYLIB NAMES
target_link_libraries(${PROJECT_NAME} 
                    ${libopencv_calib3d.4.10.0} 
                    ${libopencv_core.4.10.0} 
                    ${libopencv_dnn.4.10.0} 
                    ${libopencv_features2d.4.10.0} 
                    ${libopencv_flann.4.10.0} 
                    ${libopencv_gapi.4.10.0} 
                    ${libopencv_highgui.4.10.0} 
                    ${libopencv_imgcodecs.4.10.0} 
                    ${libopencv_imgproc.4.10.0} 
                    ${libopencv_ml.4.10.0} 
                    ${libopencv_objdetect.4.10.0} 
                    ${libopencv_photo.4.10.0} 
                    ${libopencv_stitching.4.10.0} 
                    ${libopencv_video.4.10.0} 
                    ${libopencv_videoio.4.10.0})

add_custom_command(TARGET ${PROJECT_NAME} POST_BUILD COMMAND ./bin/${PROJECT_NAME})
