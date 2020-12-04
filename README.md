ロボットシステム学 課題1
---

## 課題内容 
  
 課題: 講義で作ったデバイスドライバを改造して、LEDやモータ、あるいはその他なにかデバイスを動かせるようにして、動かしている様子を動画に撮影する。
 https://github.com/ryuichiueda/robosys_device_drivers/blob/master/myled.c
  
---
  
## 用意する物
  
・Raspberry Pi 4 ModelB  
・ブレッドボード  
・LED 2個
・ジャンパー線　7本  
・抵抗220Ω　2個

  
---
  
## 改造内容
  
　2つのLEDが同時に短い間隔で2回3回と点滅するように改造しました。  

 
 $ echo 0 > /dev/myled0 : LEDの消灯  
 $ echo 1 > /dev/myled0 : LEDの点灯  
 $ echo 2 > /dev/myled0 : LED2回点滅  
 $ echo 3 > /dev/myled0 : LED3回点滅  
  
---
  
## 実行手順
  
実行する手順は以下の通りです。  
```
$ git clone https://github.com/sasato0703/myled2.git 
$ cd myled2
$ make  
$ sudo insmod myled.ko 
$ sudo chmod 666 /dev/myled0
$ sudo [0 or 1 or 2 or 3] > /dev/myled0


```

## 動画
  プログラムを実行したデバイスドライバの様子：https://youtu.be/rb4S0RL8nXA
  


## ライセンス
https://github.com/sasato0703/myled2/blob/main/LICENSE
