# Object Detection

[![DOI](https://zenodo.org/badge/288429188.svg)](https://zenodo.org/badge/latestdoi/288429188)

Publication DOI: 10.1109/ICIEAM51226.2021.9446384

Object Detection via YOLO alorithm on DE10-NANO for Innovate FPGA

1) Install Blueoil to your desktop machine

Installation steps and supported devices can be found at

https://github.com/blue-oil/blueoil

```
$ git clone --recursive [Blueoil repository]
$ make deps
$ cd blueoil
$ make build
```
As an output there will be the docker image to work in

2) Set Up FPGA board (DE10-NANO)

Download Linux Image

```
$ wget https://storage.googleapis.com/blueoil-asia-northeast1/os-images/de10nano_ubuntu_TCAv2.img.gz
```

Insert MicroSD card into your machine

```
$ cat de10nano_ubuntu_TCAv2.img.gz | gunzip | sudo dd of=/dev/[your_target_name] bs=4M
```

Connect to the board via PuTTy serial connection

```
Serial line: /dev/ttyUSB0 (something like this, depends on connected devices)
Speed: 115200
Login: root
Password: <None> (Just press ENTER)
```

Update Python and required packages

```
$ apt-get update
$ apt-get install python-dev python-setuptools python-pip unzip
``` 

3) Get your hands on example project in https://github.com/neeveermoree/obj_det_innovate_fpga_2020/tree/master/template_project
