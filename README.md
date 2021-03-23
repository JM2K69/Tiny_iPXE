# Tiny_iPXE

iPXE solution for Windows iPXE **WDS** **MDT** **PSD** **OSDCLOUD**

# Demo

* We can boot from **any architecture**
* With ou without Menu
* Fully customizable
* We can boot from HTTPS-HTTP, iSCSI, Disk, ISO and WimFile with wimboot.

![Auhtors_img](/Resources/Tweet.PNG)


![alt](https://github.com/JM2K69/Tiny_iPXE/blob/main/Resources/img/demo.gif)

# Menu Ipxe

An example of configuration file :

```ini
#!ipxe

set boot-url http://${next-server}:8080

 cpuid --ext 29 && set arch x64 || set arch x86
  kernel ${boot-url}/wimboot quiet
  initrd ${boot-url}/BOOT/BCD         BCD
  initrd ${boot-url}/BOOT/BOOT.SDI    BOOT.SDI
  initrd ${boot-url}/SOURCES/PSD/${buildarch}/BOOT.WIM BOOT.WIM
  boot

 :unknown
 echo Unknown platform ${platform}_${buildarch}
```

# Contribution

![Tweet](https://twitter.com/ipxe/status/1362179198979366919?s=20)