# rpi-waveshare-35c

## compile this overlay
参考
https://github.com/swkim01/waveshare-dtoverlays

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

## 中断的解释
https://blog.csdn.net/xingqingly/article/details/81150670

## 触摸的问题
将 spi-max-frequency，从 32000000, 改为 2000000

## xorg配置
使用270度屏幕的触摸配置 99-calibration.conf
显示设置 dtoverlay=waveshare35c:rotate=270

## 查看fbcp输出的信息
tail /var/log/messages

## 触摸

使用现成的evdev方案，libinput不会调

sudo cp

