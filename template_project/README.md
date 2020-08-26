# Object Detection project example

To use this project you should:

1) Burn Linux Image to MicroSD via EasyRSA for example

2) Then put MicroSD card into DE10-NANO

3) Connect USB camera to the board. Make sure it is recognizible.

4) Power it up and connect to the board through SSH

```
  $ ssh -X root@{DE10-Nano's IP address}
```

5) Copy template folder and name it as demo

6) Update FPGA configuration

```
  $ cd demo/fpga
  $ sudo mount /dev/mmcblk0p1 /media
  $ cp soc_system.rbf /media
  $ dd if=preloader-mkpimage.bin of=/dev/mmcblk0p3 && sync
  $ reboot

```

7) Run Neural Network
```
  $ cd demo/python
  $ export LC_ALL=C # for the first time only
  $ sudo pip install -r requirements.txt  # for the first time only 
  $ python usb_camera_demo.py \
      -m ../models/lib/libdlk_fpga.so \
      -c ../models/meta.yaml
```



