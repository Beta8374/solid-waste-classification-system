# Tiny ML for classifying solid waste 

This project was my final project to obtain my bachelor's degree in CS.

The classification model was created entirely in Edge Impulse Studio. You can check out the project [here](https://studio.edgeimpulse.com/studio/847334) or in the description. I just made a few changes to the code, and now the result is displayed on the OLED monitor and LED. 

This is a prototype embedded system for identifying solid waste using a Convolutional Neural Network (CNN), capable of classifying waste into four classes: metal, plastic, paper, and glass. The overall accuracy is 85.7% and the F1 score is 0.86 in the quantized model. The estimated latency is around 3089 ms.

<figure>
    <img src="/imgs/confusion matrix.png" alt="Confusion matrix of the project with all classes" width="600" height="500">
    <figcaption>Confusion matrix of the project with all classes</figcaption>
</figure>

The files above may give you all the things that you need to reproduce this project, but, just in case, i use Arduino IDE (2.3.7), Adafruit_SSD1306 (v. 2.5.16) and Adafruit_GFX (v. 1.12.4). 

<figure>
    <img src="/imgs/prototype.png" alt="image of the assembled circuit." width="600" height="500">
    <figcaption>Image of the assembled circuit.</figcaption>
</figure>

## What the algorithm do

When you place an object in front of the camera, the model identifies the object and returns only one classification within the four possible classes. This process is repeated continuously, and a new result appears every three seconds. The system execution flow is shown in the image below. 

<figure>
    <img src="/imgs/execution process.png" alt="System implementation diagram" width="600" height="500">
    <figcaption>System implementation diagram</figcaption>
</figure>

<br>
Some of the limitations of this project are that the inference time is high and there is no filter to discern the background and save resources.

> [!IMPORTANT]
> - I didn't use the ESP32's built-in light; I recommend a powerful external light source on the object. Poor lighting and object positioning can affect the result.
> - **Object deteccition** is different from **classification algorithms**. 

# Important notes

> [!WARNING]
> - Make sure the FTDI module jumper is set to 5V.
> - Make sure you are using a good quality cable to power the circuit.
> - BROWNOUT DETECTION: To resolve this, I used my computer's USB 3.2 Gen 1 port. This may be related to a power surge during startup, the required amperage may be slightly higher than usual.


> [!CAUTION]
> This is just a guide; I don't recommend doing this if you don't know what you're doing. I am not responsible for any equipment damage.

<hr>
If you have any comments or ideas about this, you could contact me.
