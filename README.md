# SEEED-AI-module-on-an-esp32

...

### Installing library

Go to this github: https://github.com/Seeed-Studio/Seeed_Arduino_GroveAI

And download the repo's zip:
![dowload zip](https://github.com/user-attachments/assets/a9ecc1cd-b475-4175-93b6-4dcdcd447be8)

Then go to Arduino IDE, go to: Sketch > Include library > Add .ZIP library...
Then add the ZIP file you just downloaded. 
You can see it's dowloaden in the ooutput. 


### Starting the code file and board

Go to: File > examples > SEEED_Arduino_GroveAI > object_detection
![object detection](https://github.com/user-attachments/assets/108c2998-21be-47dc-8401-c6148e79c312)


#### connect board
Go to here: https://seeeddoc.github.io/Grove-Base_shield_v2/
... and find out which pins you should connect the grove for your board. I'm unsing a ESP32 board.

So I did:
- GND -> GND
- VCC -> 3v3
- SDA -> GPIO 21 (D22)
- SCL = GPIO 22 (D21)

Make sure to define those pins in the code:

```
#define PIN_WIRE_SDA 21
#define PIN_WIRE_SCL 22
```

