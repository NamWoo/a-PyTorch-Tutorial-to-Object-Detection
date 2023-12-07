
# pytorch and ssd

graphic driver, opencv, pytorch, gstreamer, python, cuda, cudnn, ssd


## graphic driver

```bash
sudo chmod +x ./NVIDIA-Linux-x86_64-535.113.01.run

#https://lee-jaewon.github.io/ubuntu/CUDA/
sudo vim /etc/modprobe.d/blacklist.conf
blacklist nouveau
options nouveau modeset=0
sudo update-initramfs -u
```

## cmake opencv
```bash
cmake -D CMAKE_BUILD_TYPE=RELEASE -D WITH_CUDA=ON -D WITH_1394=OFF -D BUILD_WITH_DEBUG_INFO=OFF -D BUILD_DOCS=OFF -D INSTALL_C_EXAMPLES=ON -D INSTALL_PYTHON_EXAMPLES=ON -D BUILD_EXAMPLES=OFF -D BUILD_PACKAGE=OFF -D BUILD_PERF_TESTS=OFF -D WITH_QT=OFF -D WITH_GTK=ON -D WITH_OPENGL=ON -D BUILD_opencv_python3=ON -D OPENCV_EXTRA_MODULES_PATH=../../opencv_contrib-4.8.1/modules -D WITH_V4L=ON -D WITH_FFMPEG=ON -D WITH_XINE=ON -D OPENCV_ENABLE_NONFREE=ON -D BUILD_NEW_PYTHON_SUPPORT=ON -D OPENCV_SKIP_PYTHON_LOADER=ON -D OPENCV_GENERATE_PKGCONFIG=ON -D PYTHON3_NUMPY_INCLUDE_DIRS=/usr/lib/python3/dist-packages/numpy/core/include/ -D PYTHON3_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython3.8.so -D BUILD_TIFF=ON -D BUILD_opencv_java=OFF -D WITH_OPENCL=ON -D WITH_IPP=ON -D WITH_TBB=ON -D WITH_EIGEN=ON -D BUILD_TESTS=OFF -D BUILD_opencv_python2=OFF -D CMAKE_INSTALL_PREFIX=/usr/local -D PYTHON3_INCLUDE_DIR=$(python3 -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())") -D PYTHON3_PACKAGES_PATH=$(python3 -c "from distutils.sysconfig import get_python_lib; print(get_python_lib())") -D OPENCV_ENABLE_NONFREE=ON -D PYTHON3_EXECUTABLE=$(which python3) -D PYTHON_DEFAULT_EXECUTABLE=$(which python3) -D BUILD_EXAMPLES=ON ../
```

## system check

```bash

lspci | grep -i VGA
cat /etc/lsb-release
lspci | grep VGA
uname -m && cat /etc/*release
gcc --version

v4l2-ctl --list-devices
v4l2-ctl --device /dev/video0 --all

which nvidia-smi
/usr/bin/nvcc
nvcc --version
cat /usr/local/cuda/version.txt



```


## Download the Pre-Trained Weights

[Download SSD300 Pre-Trained Weights](https://drive.google.com/file/d/1bvJfF6r_zYl2xZEpYXxgb7jLQHFZ01Qe/view)

`checkpoint_ssd300.pth.tar` in `checkpoints` folder 

## start

```bash

python3 detect_vid.py --input input/video1.mp4


```
