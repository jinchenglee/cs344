############################################################################
# <summary> CMakeLists.txt for OpenCV and CUDA. </summary>
# <date>    2012-02-07          </date>
# <author>  Quan Tran Minh. edit by Johannes Kast, Michael Sarahan </author>
# <email>   quantm@unist.ac.kr  kast.jo@googlemail.com msarahan@gmail.com</email>
############################################################################

cmake_minimum_required(VERSION 3.5)
find_package(CUDA)

include_directories(/home/vitob/libs/opencv-2.4.9/include)
link_directories(/home/vitob/libs/opencv-2.4.9/lib)
#target_link_libraries(opencv_core opencv_imgproc opencv_highgui)
#find_library(opencv_core opencv_imgproc opencv_highgui)

#find_package(OpenCV REQUIRED) # This finds opencv3.1

#link_libraries(${OpenCV_LIBS})
link_libraries(opencv_core opencv_highgui opencv_imgproc)

# collect source files

file( GLOB  hdr *.hpp *.h )
file( GLOB  cu  *.cu)
SET (HW1_files main.cpp reference_calc.cpp compare.cpp)

CUDA_ADD_EXECUTABLE(HW1 ${HW1_files} ${hdr} ${cu})
