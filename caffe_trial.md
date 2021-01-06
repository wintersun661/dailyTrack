## graphics driver download
## multiversion CUDA installation
## cudnn installation
## opencv compilation
### cmake specifictaions (with Anaconda python2 & python3)
sudo cmake -D CMAKE_BUILD_TYPE=RELEASE       
-D CMAKE_INSTALL_PREFIX="/usr/local/opencv/opencv-install/"       
-D OPENCV_EXTRA_MODULES_PATH="/usr/local/caffe_relevant/downloads/opencv_contrib/modules"        
-D BUILD_EXAMPLES=ON        
-D BUILD_opencv_python2=ON     
-D WITH_FFMPEG=1        
-D WITH_TIFF=ON        
-D WITH_CUDA=ON     
-D WITH_PROTOBUF=OFF 
-D BUILD_PROTOBUF=OFF 
-D BUILD_LIBPROTOBUF_FROM_SOURCES=OFF 
-D PROTOBUF_UPDATE_FILES=OFF        
-D ENABLE_PRECOMPILED_HEADERS=ON       
-D Protobuf_INCLUDE_DIR="/home/dyzhao/anaconda3/envs/caffe_py35/include"        
-D Protobuf_INCLUDE_DIRS="/home/dyzhao/anaconda3/envs/caffe_py35/include"        
-D PROTOBUF_LIBRARIES="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotobuf.so;-lpthread"        
-D PROTOBUF_LIBRARY="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotobuf.so"        
-D PROTOBUF_LIBRARY_DEBUG="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotobuf.so"        
-D PROTOBUF_LITE_LIBRARIES="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotobuf-lite.so"        
-D PROTOBUF_LITE_LIBRARY="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotobuf-lite.so"        
-D PROTOBUF_LITE_LIBRARY_DEBUG="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotobuf-lite.so"        
-D PROTOBUF_PROTOC_EXECUTABLE="/home/dyzhao/anaconda3/envs/caffe_py35/bin/protoc"        
-D PROTOBUF_PROTOC_LIBRARIES="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotoc.so"        
-D PROTOBUF_PROTOC_LIBRARY="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotoc.so"        
-D PROTOBUF_PROTOC_LIBRARY_DEBUG="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libprotoc.so"        
-D PYTHON2_EXECUTABLE="/home/dyzhao/anaconda3/envs/caffe_py27/bin/python"        
-D PYTHON2_INCLUDE_DIR="/home/dyzhao/anaconda3/envs/caffe_py27/include/python2.7"        
-D PYTHON2_LIBRARY="/home/dyzhao/anaconda3/envs/caffe_py27/lib/libpython2.7.so"        
-D PYTHON2_NUMPY_INCLUDE_DIRS="/home/dyzhao/anaconda3/envs/caffe_py27/lib/python2.7/site-packages/numpy/core/include"      
-D PYTHON3_EXECUTABLE="/home/dyzhao/anaconda3/envs/caffe_py35/bin/python"        
-D PYTHON3_INCLUDE_DIR="/home/dyzhao/anaconda3/envs/caffe_py35/include/python3.5m"        
-D PYTHON3_LIBRARY="/home/dyzhao/anaconda3/envs/caffe_py35/lib/libpython3.5m.so"        
-D PYTHON3_NUMPY_INCLUDE_DIRS="/home/dyzhao/anaconda3/envs/caffe_py35/lib/python3.5/site-packages/numpy/core/include"        
-D INSTALL_PYTHON_EXAMPLES=ON        
-D OPENCV_SKIP_PYTHON_LOADER=ON 
-D CUDA_TOOLKIT_ROOT_DIR=/usr/local/cuda 
-D WITH_CUDNN=ON 
-D CUDNN_INCLUDE_DIR=/usr/include 
-D CUDNN_LIBRARY=/usr/lib/x86_64-linux-gnu/libcudnn.so.8.0.5 
-D CUDNN_VERSION=8.0.5
../opencv

### make install de-error

fatal error : boostdesc_bgm.i: No such file or directory
paste (https://files-cdn.cnblogs.com/files/arxive/boostdesc_bgm.i,vgg_generated_48.i%E7%AD%89.rar)files into opencv_contrib/modules/xfeatures2d/src/

/usr/local/caffe_relevant/downloads/opencv_contrib/modules/xfeatures2d/test/test_features2d.cpp:51:10: fatal error: features2d/test/test_detectors_regression.impl.hpp: 没有那个文件或目录
 #include "features2d/test/test_detectors_regression.impl.hpp"

--solution: copy opencv/modules/features2d -> build/

/usr/bin/ld: CMakeFiles/example_gpu_surf_keypoint_matcher.dir/surf_keypoint_matcher.cpp.o: in function `main':
surf_keypoint_matcher.cpp:(.text.startup.main+0x73f): undefined reference to `cv::cuda::SURF_CUDA::SURF_CUDA()'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0x966): undefined reference to `cv::cuda::SURF_CUDA::operator()(cv::cuda::GpuMat const&, cv::cuda::GpuMat const&, cv::cuda::GpuMat&, cv::cuda::GpuMat&, bool)'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0x9fa): undefined reference to `cv::cuda::SURF_CUDA::operator()(cv::cuda::GpuMat const&, cv::cuda::GpuMat const&, cv::cuda::GpuMat&, cv::cuda::GpuMat&, bool)'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0xa9c): undefined reference to `cv::cuda::SURF_CUDA::defaultNorm() const'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0xbba): undefined reference to `cv::cuda::SURF_CUDA::downloadKeypoints(cv::cuda::GpuMat const&, std::vector<cv::KeyPoint, std::allocator<cv::KeyPoint> >&)'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0xbda): undefined reference to `cv::cuda::SURF_CUDA::downloadKeypoints(cv::cuda::GpuMat const&, std::vector<cv::KeyPoint, std::allocator<cv::KeyPoint> >&)'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0xbf0): undefined reference to `cv::cuda::SURF_CUDA::downloadDescriptors(cv::cuda::GpuMat const&, std::vector<float, std::allocator<float> >&)'
/usr/bin/ld: surf_keypoint_matcher.cpp:(.text.startup.main+0xc02): undefined reference to `cv::cuda::SURF_CUDA::downloadDescriptors(cv::cuda::GpuMat const&, std::vector<float, std::allocator<float> >&)'
collect2: error: ld returned 1 exit status

--solution:
modify <build_dir>/samples/gpu/CMakeFiles/example_gpu_surf_keypoint_matcher.dir/link.txt 
(CMakeFiles/example_gpu_surf_keypoint_matcher.dir/surf_keypoint_matcher.cpp.o) /usr/local/caffe_relevant/downloads/build/modules/xfeatures2d/CMakeFiles/opencv_xfeatures2d.dir/src/surf.cuda.cpp.o /usr/local/caffe_relevant/downlodas/build/modules/xfeatures2d/CMakeFiles/cuda_compile_1.dir/src/cuda/cuda_compile_1_generated_surf.cu.o -o .....”


/usr/local/caffe_relevant/downloads/opencv/modules/python/src2/cv2.cpp:33:10: fatal error: numpy/ndarrayobject.h: 没有那个文件或目录
 #include <numpy/ndarrayobject.h>
          ^~~~~~~~~~~~~~~~~~~~~~~
compilation terminated.

--solution 
sudo apt-get install python-numpy

useful links :
https://blog.csdn.net/GungnirsPledge/article/details/108597474
## opencv successfully built!!

sudo make install
sudo ln -s /usr/local/opencv/opencv-install/lib/python2.7/site-packages/cv2.so /home/dyzhao/anaconda3/envs/caffe_py27/lib/python2.7/site-packages/cv2.so
sudo ln -s /usr/local/opencv/opencv-install/lib/python3.5/site-packages/cv2.cpython-35m-x86_64-linux-gnu.so  /home/dyzhao/anaconda3/envs/caffe_py35/lib/python3.5/site-packages/cv2.so

### test if successfully installed in corresponding python-conda envs，
conda install numpy
python
import cv2

caffe_py27 passes easily

caffe_py35:
ImportError: No module named 'numpy.core._multiarray_umath'
pip install numpy --upgrade

Installing collected packages: numpy
  Found existing installation: numpy 1.15.2
    Uninstalling numpy-1.15.2:
      Successfully uninstalled numpy-1.15.2
Successfully installed numpy-1.18.5

successfully import cv2!!

opencv version 4.2.0


## caffe compilation
#error PROTOBUF_DEPRECATED was previously defined
 #error PROTOBUF_DEPRECATED was previously defined
 
error: ‘const class caffe::V0LayerParameter’ has no member named ‘GetArenaNoVirtual’


error: ‘google::protobuf::io::EpsCopyOutputStream’ has not been declared

##to be further updated -0106













