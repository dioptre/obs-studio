# OBS Studio 

This is my fork of OBS Studio with support for queuing of files and realtime playback of video effects. It's especially useful for artists wanting to queue up and mix video effects live.

Feel free to ask questions!


## Installing on debian or ubuntu
Get the dependencies:
```
sudo apt install software-properties-common -y && \
sudo apt-add-repository non-free && \
sudo apt-get update
```
Then:
```
sudo apt-get install \
           build-essential \
           checkinstall \
           cmake \
           git \
           libmbedtls-dev \
           libasound2-dev \
           libavcodec-dev \
           libavdevice-dev \
           libavfilter-dev \
           libavformat-dev \
           libavutil-dev \
           libcurl4-openssl-dev \
           libfdk-aac-dev \
           libfontconfig-dev \
           libfreetype6-dev \
           libgl1-mesa-dev \
           libjack-jackd2-dev \
           libjansson-dev \
           libluajit-5.1-dev \
           libpulse-dev \
           libqt5x11extras5-dev \
           libspeexdsp-dev \
           libswresample-dev \
           libswscale-dev \
           libudev-dev \
           libv4l-dev \
           libvlc-dev \
           libx11-dev \
           libx264-dev \
           libxcb-shm0-dev \
           libxcb-xinerama0-dev \
           libxcomposite-dev \
           libxinerama-dev \
           pkg-config \
           python3-dev \
           qtbase5-dev \
           libqt5svg5-dev \
           swig \
           libxcb-randr0-dev \
           libxcb-xfixes0-dev \
           libx11-xcb-dev \
           libxcb1-dev -y
```

Then build (with browser source):
```
wget https://cdn-fastly.obsproject.com/downloads/cef_binary_3770_linux64.tar.bz2
tar -xjf ./cef_binary_3770_linux64.tar.bz2
git clone --recursive https://github.com/dioptre/obs-studio.git
cd obs-studio
mkdir build && cd build
cmake -DUNIX_STRUCTURE=1 -DCMAKE_INSTALL_PREFIX=/usr -DBUILD_BROWSER=ON -DCEF_ROOT_DIR="../../cef_binary_3770_linux64" ..
make -j4
sudo make install
```
Or without browser source:
```
git clone --recursive https://github.com/dioptre/obs-studio.git
cd obs-studio
mkdir build && cd build
cmake -DUNIX_STRUCTURE=1 -DCMAKE_INSTALL_PREFIX=/usr ..
make -j4
sudo make install
```
## Running
After you've followed the instructions above just run:
```
obs
```
