# **Building my own Dactyl Manuform**
![dactyl-manuform](https://github.com/user-attachments/assets/a260f913-8e95-4360-991b-0608cc329065)

## **What is a dactyl-manuform?**
[Dactyl-Manuform](https://github.com/abstracthat/dactyl-manuform) is an open source fork of the famous 3D printed [Dactyl Keyboard](https://github.com/adereth/dactyl-keyboard) by [Matt Adereth](https://github.com/adereth).

This keyboard features a split layout where the columns will be staggered instead of the rows. This shape is inspired by the early ergonomic keyboard designs. This layout helps the user rest their arms in a naturally neutral position. [This provides comfort and prevents RSI.](http://xahlee.info/kbd/i2/split_keyboard__david_Rempel_2008_HF.pdf). 

What I have assembled is [another fork](https://github.com/markdhooper/CMD-dactyl-manuform) of the Dactyl Manuform fork. This layout is slightly different. There is an extra column, row and extra thumb keys.  

I assembled this keyboard as a hobby project and for one of my university projects. The steps taken to build this is briefly explained below.  


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
  The wiring of a keyboard is a kind of matrix circuits. A typical keyboard employs a matrix circuit to register key presses efficiently. For example, in this keyboard we will have about 72 keys (36 on each half). The microcontroller we are using does not have 72 pins to account for all 72 keys. For cases like this we employ a matrix like circuit.
  Imagine a grid where each row corresponds to a set of keys and each column represents another set. When you press a key, it completes a circuit between its corresponding row and column. This intersection uniquely identifies the pressed key based on its row and column coordinates. To manage this, the keyboard controller scans each row of the matrix sequentially. It checks the status of each column to detect any completed circuits (key presses). This scanning happens rapidly, usually faster than human perception, ensuring real-time responsiveness.
  When a key press is detected, the controller identifies which row and column are involved, thereby determining which key was pressed. This information is then sent to the computer as an input signal. Keyboards typically use diodes to prevent ghosting and ensure accurate key detection, allowing multiple keys to be pressed simultaneously without confusion. This matrix arrangement efficiently reduces the number of wires needed, making keyboards compact while maintaining functionality. For the diodes in this build we are using the 1N4148 diodes.
  From the figure 3-2 we can see that the number of columns on each side is 7 and the number of rows on each side is 5. Hence this is known as the 5x7 variant of dactyl-manuform. Between each of the column connections between each key we will be soldering a diode to ensure that the flow of electricity is one-way to avoid ghosting issues.
Here we can also observe the inner working of the thumb cluster. From the outside one would assume that the thumb cluster of the keyboard is a separate column and row structure in the circuit. However, for simplifying the circuit we can see that the column 3,4,5 and 6 are continued to make up for the columns and the rows 6 covers all the thumb keys. Even though here we can see that the row 6 adds another row of keys it is not counted when giving the conventional name to this variant of the keyboard.
  Human hands are very versatile and it helped our species to make and create tools that led to the current day civilization. The thumb of our hands is one of the strongest muscles but unfortunately it does not shine while typing on a normal keyboard. To utilize this very strong point of our hands ergonomic keyboards have a very wide selection of keys that are made for the thumbs.


### 4. 

// process 

// conclusion

