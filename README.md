# install-in-ubuntu 16.04.4
[[install code in ubuntu]]

system update

    sudo apt-get update && sudo apt-get upgrade && sudo apt-get dist-upgrade

pcl

    sudo apt-get install libpcl-dev 

boost

    sudo apt-get install libboost1.55-all-dev

eigen

    sudo apt-get install libeigen3-dev

qhull

    sudo apt-get install libqhull-dev

flann

    sudo apt-get install libflann-dev

VTK

    sudo apt-get install libvtk6-dev libvtk6.2

opencv3.1 deps

    sudo apt-get install build-essential libgtk2.0-dev libvtk5-dev libjpeg-dev libtiff5-dev libjasper-dev libopenexr-dev libtbb-dev

opencv3.4.0 deps

    sudo apt-get install git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
    sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libdc1394-22-dev

mesa

    sudo apt-get install mesa-common-dev mesademos libgl1-mesa-dev libglu1-mesa-dev freeglut3-dev
    
OpenBLAS

    sudo apt-get install libopenblas-dev liblapack-dev 
    
opencl

    sudo apt-get install beignet-dev
    
openni2

    sudo apt-get install -y g++ python libusb-1.0-0-dev freeglut3-dev doxygen graphviz
    sudo apt-get install libudev-dev 
    apt-cache search openni2
    sudo apt-get install libopenni2-dev 
    
gcc g++ version

    cd /usr/bin
    sudo apt-get install -y gcc-4.8
    sudo apt-get install -y g++-4.8
    sudo rm gcc 
    sudo rm g++ 
    sudo ln -s gcc-4.8 gcc
    sudo ln -s g++-4.8 g++
    
cuda

    if [[ $version == *"14.04"* ]] ; then
         wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1404/x86_64/cuda-repo-ubuntu1404_7.5-18_amd64.deb
         sudo dpkg -i cuda-repo-ubuntu1404_7.5-18_amd64.deb
         rm cuda-repo-ubuntu1404_7.5-18_amd64.deb
         sudo apt-get update
         sudo apt-get install cuda-7-5
     elif [[ $version == *"15.04"* ]] ; then
         wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1504/x86_64/cuda-repo-ubuntu1504_7.5-18_amd64.deb
         sudo dpkg -i cuda-repo-ubuntu1504_7.5-18_amd64.deb
         rm cuda-repo-ubuntu1504_7.5-18_amd64.deb
         sudo apt-get update
         sudo apt-get install cuda-7-5
     elif [[ $version == *"16.04"* ]] ; then
         wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.44-1_amd64.deb
         sudo dpkg -i cuda-repo-ubuntu1604_8.0.44-1_amd64.deb
         rm cuda-repo-ubuntu1604_8.0.44-1_amd64.deb
         sudo add-apt-repository ppa:openjdk-r/ppa 
         sudo apt-get update
         sudo apt-get install cuda-8-0
     else
         echo "Don't use this on anything except 14.04, 15.04, or 16.04"
         exit
     fi
     
python opendr
     pip install opendr==0.77
