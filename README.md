# JCW-Pro-Exhaust-Controller

this simple project was born from the personal need to solve an annoying problem with the bluetooth remote control of my JCW Pro exhaust. I am not responsible for any damage to third parties or objects, including the car. This publication is for the sole purpose of my memory.

The exhaust valve is controlled by a 12v powered control unit located in the trunk. The control unit is not a simple relay, the valve is controlled by a PWM circuit and opens / closes according to the supplied voltage. Not having an oscilloscope I was not able to determine the duty cycle of the PWM control, however by jumpering the control signal to GND I saw that the valve actually opens. Therefore, by inserting a relay after the control unit, it is possible to remotely control the jumper.

![WhatsApp Image 2022-07-11 at 09 04 03](https://user-images.githubusercontent.com/4238515/178209231-50427850-8ea5-48d1-b558-4d04fb22d71e.jpeg)


Using 3 t-tap junction connector I took:
-12v (red cable) and GND (black cable) coming from the fuse box that power the control unit itself;
- PWM signal (cable indicated by the arrow).

![WhatsApp Image 2022-07-11 at 09 04 50](https://user-images.githubusercontent.com/4238515/178210078-6264a7c3-3225-468e-9036-4caf16979ba5.jpeg)

As a relay I chose an ESP8266 wifi board (about 7-9 euros) and I created a simple firmware based on ESPHome (https://esphome.io). This creates a wifi access point called JCW PRO with password 12345678 and integrates a webserver to control the relay at page http://192.168.4.1
Being a simple wifi network and a web page, it is compatible with any device, iOS-Android-Windows etc. and future-proof.

The card I bought is this:
https://www.amazon.it/dp/B07DJ4X4MX/?coliid=I1RMNTGA2TS3SI&colid=16RC7Q1DO2FU7&psc=1&ref_=lv_cv_lig_dp_it

On the board it's write ESP8266 RELAY V3 - LC TECHNOLOGY
Pay attention that these cards exist in both 5v and 12v versions, the one you need is 12v.

Then the links:

12v (red cable) from the fuse box ---> +IN of the board
GND (black cable) from the fuse box ---> -IN of the board
PWM (cable to be jumpered) ---> NO (for valve open by default) or NC (for closed by default)
Also a jumper between COM and -IN
