# opencv3_Cpp_Mac

### Download/Unzip Opencv3.4
OpenCv3.4 is a more stable version than version 4.*
```
curl -L0k  https://github.com/opencv/opencv/archive/3.4.5.zip > opencv-3.4.zip
unzip opencv-3.4.zip -d opencv-3.4
mv opencv-3.4/opencv-3.4.5 . && rm opencv-3.4 && mv opencv-3.4.5 opencv-3.4
rm opencv-3.4.zip
```

### Install CMake through Brew
```
brew install cmake
# verify if cmake is in /usr/local
brew ls cmake
```

### Build opencv3 binary source using cmake
```
# create a build directory
cd opencv-3.4
mkdir build

# call cmake to build
cd build
# this will install what OpenCV needs to run
cmake -G "Unix Makefiles" ..
make -j4
# install opencv to system
make install
```

### Setup Xcode Project
* MacOS > select `Command Line Tool`
* Go to `Build Settings`:
  ** Always Search User Path: true
  ** Header Search Paths:  `/usr/local/include`
  ** Library Search Paths: `/usr/local/lib`
  ** Other Linker Flags: `-lopencv_calib3d -lopencv_core -lopencv_features2d -lopencv_flann -lopencv_highgui -lopencv_imgcodecs -lopencv_imgproc -lopencv_ml -lopencv_objdetect -lopencv_photo -lopencv_shape -lopencv_stitching -lopencv_superres  -lopencv_video -lopencv_videoio -lopencv_videostab`

### main.cpp
```
#include <iostream>
#include <opencv2/core.hpp>

int main(int argc, const char * argv[]) {
    // insert code here...
    std::cout << "OpenCV version: " << CV_VERSION << std::endl;
    return 0;
}
```
### This should print out the version of OpenCV attached to the workspace.
