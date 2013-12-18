How to compile and run your program under android on pcDuino
===============================================================
1. the old way, cross-comple command-line programs from PC.
 or build qt-android-apk with qcreator, please refer to: 
 
https://github.com/liaods/c_enviroment_android
Write a Simple Command-Line Program to Control Hardware under Android on pcDuino
http://www.pcduino.com/?p=1519
Quick Start Guide on setup QT5 for Android on pcDuino
http://www.pcduino.com/?p=1494

2. compile you program on pcDuino (native compile)
1) Get the toolchain and pcduino libs from https://github.com/liaods/pcduino-gcc-on-android

2) Open Terminal APK, and run the following commands
$ su
# busybox tar zxvf pcduino-android-gcc-20131218.tgz -C /data/
# busybox tar zxvf pcduino-android-arduino-20131218.tgz -C /data/

3) write your code and save it(with busybox vi or other gui tools), for example /data/blink_led.c

#include <Arduino.h>
int led_pin = 18; // pcduino TX LED

void setup()
{
    pinMode(led_pin, OUTPUT);
}

void loop()
{
    digitalWrite(led_pin, HIGH);
    delay(1000);
    digitalWrite(led_pin, LOW);
    delay(1000);
}

4) compile and run
before this step, run env.sh to setting up the enviroment
# . /data/pcduino-android-gcc/env.sh
# pcduino-cc blink_lec.c
target is blink_led
run it:
#./blink_led
Press Ctrl + C to stop it!