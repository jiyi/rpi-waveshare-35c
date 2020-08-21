# rpi-waveshare-35c

## compile this overlay
```
dtc -@ -Hepapr -I dts -O dtb -o waveshare35c.dtbo waveshare35c.dts
```



## compile wanning
编译时出现以下警告
```
waveshare35c.dtbo: Warning (unit_address_vs_reg): /fragment@0/__overlay__/spidev@0: node has a unit name, but no reg property
waveshare35c.dtbo: Warning (unit_address_vs_reg): /fragment@0/__overlay__/spidev@1: node has a unit name, but no reg property
```
通过这个网址的建议，消除了警告
https://www.raspberrypi.org/forums/viewtopic.php?t=172342


## 理解源代码
https://www.kernel.org/doc/Documentation/devicetree/bindings/gpio/gpio.txt