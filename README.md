# Arduino_io

## 功能

通过 IO 的输出与输入，实现按键控制 LED 灯的亮灭

## 代码

```C
#include "Arduino.h"
// 设置各引脚别名
const int buttonPin = 35;     // 连接按键的引脚
const int ledPin =  18;      // 连接LED的引脚

// 变量定义
int buttonState = 0;         // 存储按键状态的变量

void setup() {
  // 初始化LED引脚为输出状态、按键引脚为输入状态
  pinMode(ledPin, OUTPUT);      

  pinMode(buttonPin, INPUT);     
}

void loop(){
  // 读取按键状态并存储在变量中
  buttonState = digitalRead(buttonPin);

  // 检查按键是否被按下
  // 如果按键按下，那buttonState应该为高电平
  if (buttonState == HIGH) {     
    // 点亮LED
    digitalWrite(ledPin, HIGH);  
  } 
  else {
    // 熄灭LED
    digitalWrite(ledPin, LOW); 
  }
}

```
