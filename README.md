Generic MediaTek MT6582 device.
==============

MediaTek MT6582 hardware released in Q3 of 2013 by MediaTek is low-end processor found almost in every cheap device. 

Basic   | Spec Sheet
-------:|:-------------------------
CPU     | 1.3GHz Quad-Core MT6582
GPU     | Mali-400MP
Memory  | 1GB RAM
Shipped Android Version | 4.2.2 - 4.4.2
Storage | 8GB (varies)
Display | 6.0" 1280 x 720 px (certainly for j805)
Camera  | 8MPx, LED Flash

![Android One](http://g01.a.alicdn.com/kf/HTB17k.bIFXXXXaIXFXXq6xXFXXXt/MEDIATEK-MTK-CPU-ARM-MT6582-MT6582V-MT6582V-U-MT6582V-U-MT6582VU-NEW-ORIGINAL.jpg "MT6582 processor")

This branch is for building CyanogenMod 12.1 (or CM-12.1 based) ROMS.

# Build

* Working
  * Dual SIM
  * Wifi
  * Bluetooth
  * Audio
  * Sensors
  * Camera (photo and video recording)
  * GPS
  * NFC (removed)
  * OTG
  * Tethering (Wifi, Bluetooth and USB)
  * FM Radio (removed)

* Compilation

        # repo init -u git://github.com/rohantaneja/android.git -b cm-12.1
        
        # repo sync
        
        # source build/envsetup.sh
        
        # brunch cm_mt6582-userdebug

# MTK

Few words about mtk related binaries, services and migration peculiarities.

# Limitations

Services requires root:

`system/core/rootdir/init.rc`

  * surfaceflinger depends on sched_setscheduler calls, unable to change process priority from 'system' user (default user 'system')

  * mediaserver depends on /data/nvram folder access, unable to do voice calls from 'media' user (default user 'media')
