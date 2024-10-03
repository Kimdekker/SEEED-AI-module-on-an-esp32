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


#### connect board and run example code
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

But you'll see that that doesn't work. 
To help this error dissapear, we'll have to hardcode something in the file from the library. 
So we've got to head over there. Go to (on your local PC): .../Documents/Arduino/libraries/Seeed_Arduino_GroveAI/Seeed_Arduino_GroveAI.h

Open this file in your code editor. I use VSCode.

Then find this line:
```
WEI(TwoWire &wire_com = Wire, uint32_t pinSDA = PIN_WIRE_SDA, uint32_t pinSCL = PIN_WIRE_SCL): _wire_com(&wire_com), _pinSDA(pinSDA), _pinSCL(pinSCL) {}
```

And recplace the whole line to:
```
WEI(TwoWire &wire_com = Wire, uint32_t pinSDA = PIN_WIRE_SDA, uint32_t pinSCL = PIN_WIRE_SCL): _wire_com(&wire_com), _pinSDA(pinSDA), _pinSCL(pinSCL) {}
```
Then save the file and close it. 

Now go back to your file on Arduino IDE and upload the code again.
In the serial monitor you now see things running. Try aiming the camera on people, and it should show it's counting people and a confidence score. 
Thats good!

#### Run it in Chrome

Now that it works, we can connect the camera with the USB-C cable to our PC and let Chrome run the Facial recognition.

Chrome will come up with a popup:
![chrome](https://github.com/user-attachments/assets/32a7de5e-8534-487a-a05d-09893dfb0645)

Click on this popup and you will be lead to this:
![chromeseeed](https://github.com/user-attachments/assets/a269e43a-6fac-485a-8773-7efe7987199e)

Then click on the "connect" button and choose Grove AI and click connect:
![connect](https://github.com/user-attachments/assets/ef9e376f-fdac-4cc2-b29b-d73a6b122bfc)

Now you'll see the camera works:
![cameraworks](https://github.com/user-attachments/assets/e8978831-98aa-466b-94ff-19b012ad27fb)

Try aiming it on people/faces and you can see how good it will work!

![facialrecognition](https://github.com/user-attachments/assets/96f40bf6-9aef-47af-a024-a15c11ad304c)


