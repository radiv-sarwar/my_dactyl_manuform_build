# **Building my own Dactyl Manuform**
![dactyl-manuform](https://github.com/user-attachments/assets/a260f913-8e95-4360-991b-0608cc329065)

## **What is a dactyl-manuform?**
[Dactyl-Manuform](https://github.com/abstracthat/dactyl-manuform) is an open source fork of the famous 3D printed [Dactyl Keyboard](https://github.com/adereth/dactyl-keyboard) by [Matt Adereth](https://github.com/adereth).

This keyboard features a split layout where the columns will be staggered instead of the rows. This shape is inspired by the early ergonomic keyboard designs. This layout helps the user rest their arms in a naturally neutral position. [This provides comfort and prevents RSI.](http://xahlee.info/kbd/i2/split_keyboard__david_Rempel_2008_HF.pdf). 

What I have assembled is [another fork](https://github.com/markdhooper/CMD-dactyl-manuform) of the Dactyl Manuform fork. This layout is slightly different. There is an extra column, row and extra thumb keys.  

I assembled this keyboard as both a hobby project and for one of my university projects. If you want a detailed breakdown of the assembly process you can check the report I submitted in university. Alternatively you can also watch this [video](https://www.youtube.com/watch?v=CxNKWNKBLMs&t=9s) by the original author of the fork I used. 

The steps taken to build this is briefly explained below.  


### 1. Print the shell/case with a 3d printer
  I did not have a 3D printer of my own as a broke college student at the time. Instead I sent the .stl files to a 3D printing service. They printed the shell and sent me the parts. I pushed in all the swtiches and keycaps. The keycaps used here are the ergodox keycaps. Ergodox is a famous consumer split keyboard. The keycaps fit perfectly with this version of the layout.
![assembled_without_paint](https://github.com/user-attachments/assets/5b762a97-019d-4ef1-983f-5ee9cd173c93)

### 2. Two Microcontrollers of your choice (I chose arduino pro-micros)
  Each half of the keyboard is operated by a microchip. There are several microchips used to build custom keyboards arduino pro micro, nice!nano, and even teensy. For this keyboard I handwired all the rows and columns in a matrix like grid (along with diodes to avoid ghosting/ phantom keys) and soldered the connetions directly with an arduino pro-micros. 
  If anyone wants to build this keyboard I would suggest not going with the cheap chinese arduino pro-micros. Their micro-usb socket is very fragile. I have broken a few of them just trying to connect the wires. 

### 3. Handwire and Solder the matrix circuit 
  This is a very soldering heavy project. I would describe the soldering as more tedious than hard. It takes a while to solder every joint but the soldering itself is much more forgiving than what I have dealt with in other projects. 
  You can skip this process by sourcing a flexible PCB for this keyboard. But that would add more cost and for a college student like me at the time, this was not a viable choice. 
![handwiring the matrix circuit](https://github.com/user-attachments/assets/ccdccf0a-c168-4ce2-96e5-005ce3b04854)
![image](https://github.com/user-attachments/assets/7e7498c8-53b5-488d-ad39-9c0627fac342)
  In this version of the layout, the keyboard has 7 columns and 5 rows per side, totaling 72 keys. Each key press connects a specific row and column, which the controller scans rapidly to identify the specific key. Diodes(1N4148 in this case), are used to prevent ghosting by allowing current to flow only in one direction, ensuring accurate detection even with multiple key presses. Thus we achieve n-key rollover.

The thumb cluster, designed for ergonomic typing, shares columns 3 to 6 with the rest of the keyboard and uses row 6 for thumb keys. Despite this, it doesn’t add extra rows in the matrix naming. This layout reduces wiring complexity while allowing for effective key registration and improved comfort.

  Each of the sides have a TRRS jack connected. We use a regular aux cable to connect the jacks. Both halves communicate with each other using this aux cable.


### 4. Flash the firmware
  There are a few options for compiling the firmware when it comes to custom keyboards like QMK and ZMK. QMK is more popular and it has a [stellar documentation page](https://docs.qmk.fm/) for setting up a proper environment for compiling your firmware. 
  
  For beginners, it's recommended to use the [QMK Configurator wesite](https://config.qmk.fm/#/zykrah/fuyu_hs/LAYOUT_all). This is a handy website where you can select your layout and change the default keymapping. [Here](https://config.qmk.fm/#/handwired/dactyl_manuform/5x7/LAYOUT_5x7) is the default version of the dactyl manuform layout that I used.
  
  Initially I used the configurator website to build and compile a version of the firmware with the default keymaps. Later on I used the qmk documentation to set up an environment on my linux machine and change some of the default keymappings according to my liking. You can also setup the environment in windows if that is what you prefer. I tried both and I liked the linux setup better. We generally use QMK MSYS to set everything up in windows as shown in the screenshot below. 
  ![image](https://github.com/user-attachments/assets/5b9cd560-50a2-405c-b379-a79cba94e6f4)
[Here](https://youtu.be/ECmdK3r2yTw) is also a rant about me fixing this keyboard after one of the micro-usb port of the microcontroller broke off the PCB. I also show a typing test and explain of using QMK MSYS on windows to solve an issue I was having with the firmware. 
  In the firmware you will have access to a config file that you can edit according to your preferences. For example, I changed the master side (the side connected to the computer) from left side to right side. I did this because the connector port of the arduino pro-micro on the left side broke. By changing the master side I was then able to connect the right side with the pc. Now the left side sends signals to the right microcontroller and the right side manages all the input signals going to the computer. I explain this in the [video I linked](https://youtu.be/ECmdK3r2yTw). 
  
### (optional) 5. Paint it! 
  I painted the white shell with some grey gunmetal pigment. I used an airbrush. This process could've yielded better results if I wasn't so impatient with the paint. I learned a lot about the painting process by doing this step. I recommend painting your dactyl if you ever make one. Its a great opportunity to personalize it however you want. The sanding process is extremely tedious tho. Beware of that. 
![just_painted](https://github.com/user-attachments/assets/75fd8e4f-1f84-40ca-862f-3dc1b8a25e26)
This is just after applying the finishing layer of paint.

![painted](https://github.com/user-attachments/assets/a5403269-f59c-498e-8ee7-c97826f1da62)
This is the final product without connecting the TRRS jacks and a usb cable. 

