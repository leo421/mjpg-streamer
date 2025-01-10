树莓派安装配置
====
本文介绍在RaspberryPi 2B中编译安装和使用 mjpg-streamer

编译和安装
====
必须先安装cmake和libjpeg

    sudo apt-get install cmake gcc g++

libjpeg安装方式比较特别

    sudo apt-get install aptitude
    sudo aptitude install libjpeg-dev

编译安装

    cd mjpg-streamer-experimental
    make
    sudo make install

运行
====

    export LD_LIBRARY_PATH=.
    ./mjpg_streamer -o "output_http.so -w ./www" -i "input_uvc.so -r FHD -fps 20"

用浏览器访问如下地址

    http://<mjpg-streamer ip>:8080/?action=stream

参数
----
插件 input_uvc.so 参数：

    -r QQVGA QCIF CGA QVGA CIF PAL VGA SVGA XGA HD SXGA UXGA FHD 或者自定义，例如：1920x1080
