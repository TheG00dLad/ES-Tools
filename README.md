# ES-Tools
This repository will be a source for different tools to use in embedded systems cases.
This is for me so dont be mean >:(

# Choosing MCU
https://ie.rs-online.com/web/p/microcontroller-development-tools/1438574 - They are all the same price, this one has a 16bit adc and is a low power option.

ESP 32 vs. STM 32.
Having experience with STM 32 I have no idea what the difference is at all. 
The STM 32 seems optimised for lower power operations, which is perfect for polling.
Both use the open source PlatformIO platform so it seems to be a use case.
I am going to attach a guide here for further reference to return to.
An important note for the STM32 is that it is used more in industry, and therefore using the system will provide a greater experience.
Also I own one, and they are cheaper by about 5 euro.

https://www.lisleapex.com/blog-esp32-vs-stm32-which-is-better

This image demonstrates how the analog section of the STM32 would be perfect.
Need to check if it is optimal.
- Not at 50 euro a chip.
![image](https://github.com/user-attachments/assets/a040cdde-ec3c-496c-97e0-cce4583613ba)
- Realistically need an maybe 3 ADC's, or 2 and an inbuilt temp sensor.
- Need to atleast 1 internal op amp for the load cell
- If the single temperature & humidity sensor works with it all inbuilt, there is less stress.

# Theorecital Resolutions
Load cell is roughly 100kg/16 bit => 100kg/2^16-1 = 1.53g/DU.
Voltage resolution is 3.3V/16 bit = 50.35uv/DU
# Design
## [ ] LoRa Devices
https://ie.rs-online.com/web/p/lpwan/0316157?gb=s

https://ie.rs-online.com/web/p/lpwan/2647778?gb=s
https://ie.rs-online.com/web/p/lpwan/9033059?gb=s
## [ ] Weighing Scales
To weigh a item of roughly 5 to 80 kg depending, a load cell of some sort is needed.
Outdoor applications are needed, so a IP65 rating is desired.
https://docs.rs-online.com/c584/A700000011099057.pdf
The input on this model is 1 +- 0.15 mV/V. A simple gain op amp will therefore be required.
It shall run off the microcontroller.
This is a compression style load cell, which is perfect for placing objects on.
A four cell design would be a better choice, due to the fact the desired item could be quite large.
With the cost of this cell, a four cell design would be easiest.
Technical testing will be needed.

![image](https://github.com/user-attachments/assets/c9e1730f-6496-4467-bbd1-4686672334ed)

## [ ] Reciever Alert
SMS messages?

https://randomnerdtutorials.com/sim900-gsm-gprs-shield-arduino/
## [ ] Temperature Sensor


## [ ] Humidity Sensor
https://ie.rs-online.com/web/p/temperature-humidity-sensor-ics/2626175
I dont know how to surface mount. :(

https://sensirion.com/media/documents/643F9C8E/63A5A436/Datasheet_SHTC3.pdf
![image](https://github.com/user-attachments/assets/f3ee4a2a-0395-43f6-93e6-3a3d7d862e3c)

This sensor is able to meaure temperature & humidity through I2C.
It has a voltage supply of 1.62 to 3.6V.
However stress voltage is at >2.16V.
