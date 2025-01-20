# **Building my own Dactyl Manuform**
![dactyl-manuform](https://github.com/user-attachments/assets/a260f913-8e95-4360-991b-0608cc329065)

## **What is a dactyl-manuform?**
[Dactyl-Manuform](https://github.com/abstracthat/dactyl-manuform) is an open source fork of the famous 3D printed [Dactyl Keyboard](https://github.com/adereth/dactyl-keyboard) by [Matt Adereth](https://github.com/adereth).

This keyboard features a split layout where the columns will be staggered instead of the rows. This shape is inspired by the early ergonomic keyboard designs. This layout helps the user rest their arms in a naturally neutral position. [This provides comfort and prevents RSI.](http://xahlee.info/kbd/i2/split_keyboard__david_Rempel_2008_HF.pdf). 

What I have assembled is [another fork](https://github.com/markdhooper/CMD-dactyl-manuform) of the Dactyl Manuform fork. This layout is slightly different. There is an extra column, row and extra thumb keys.  

I assembled this keyboard as a hobby project and for one of my university projects. The steps taken to build this is briefly explained below.  

![assembled_without_paint](https://github.com/user-attachments/assets/5b762a97-019d-4ef1-983f-5ee9cd173c93)
### 1. Print the shell/case with a 3d printer
  I did not have a 3D printer of my own as a broke college student at the time. Instead I sent the .stl files to a 3D printing service. They printed the shell and sent me the parts. I pushed in all the swtiches and keycaps. The keycaps used here are the ergodox keycaps. Ergodox is a famous consumer split keyboard. The keycaps fit perfectly with this version of the layout.
  

### 2. Two Microcontrollers of your choice (I chose arduino pro-micros)
  Each half of the keyboard is operated by a microchip. There are several microchips used to build custom keyboards arduino pro micro, nice!nano, and even teensy. For this keyboard I handwired all the rows and columns in a matrix like grid (along with diodes to avoid ghosting/ phantom keys) and soldered the connetions directly with an arduino pro-micros. 
  If anyone wants to build this keyboard I would suggest not going with the cheap chinese arduino pro-micros. Their micro-usb socket is very fragile. I have broken a few of them just trying to connect the wires. 


![handwiring the matrix circuit](https://github.com/user-attachments/assets/ccdccf0a-c168-4ce2-96e5-005ce3b04854)
### 3. Handwire and Solder the matrix circuit 
  This is a very soldering heavy project. I would describe the soldering as more tedious than hard. It takes a while to solder every joint but the soldering itself is much more forgiving than what I have dealt with in other projects. 
  You can skip this process by sourcing a flexible PCB for this keyboard. But that would add more cost and for a college student like me at the time, this was not a viable choice. 

### 4. 

// process 

// conclusion

