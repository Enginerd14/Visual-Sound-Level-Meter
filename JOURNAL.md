## xx/xx/25 - Researching methods
I looked into the various methods of making a VU meter. One of the methods I discovered was using a Programmable Integrated Circuit (PIC)  such as the Genie 20. The Genie 20 has seven output pins allowing it to power seven LEDs as the visual indicator for the VU meter. Each LED would require a 220Ω adding to the bill of materials. Using a programmable circuit, I can use a flowchart to control the chip and control which LEDs turn on depending on the signal level. I used circuit wizard to create both the circuit and the flowchart. Screenshots can be found below. In the flowchart, the analogue signal box checks if the input signal matches the signal range that I have provided. The range goes from 0 to 255 and I split this equally to determine which LEDs will turn on. In my circuit, I used an LDR for visual representation as Circuit wizard does not have a microphone as one of the available components so the LDR acts as the analogue signal that would be coming from the microphone. I can then program the flowchart in multiple ways: I could either have the LEDs move from the middle going outwards as the volume increases or have them move from bottom to top instead. This makes this method a very flexible and customisable circuit. 


I found another way of making a VU meter. This can be done through a LED bar graph and a LM39_ _ IC. The LED bar graph is composed of 10 LEDs stacked on top of each other to create a visual scale using light and colour. Most LEDs require resistors and this is the same for the LED bar graph. However, the LM39_ _,which is bar graph driver IC that is complementary to the LED bar graph, has a built in network of resistors within the chip itself. Thus, I will not require ten extra LEDs for the LEDs, reducing the bill of materials for my project.  The LM39_ _ driver comes in 3 variations: LM3914, LM3915 and LM3916. The LM3914 is a linear display used mainly in alarms and voltmeters. The LM3915 is a logarithmic display incremented by 3dB to turn each LED on after the previous one making it a good contender for a VU meter. The LM3916 is designed specifically for a VU meter which is a volume unit meter or also known as an audio visualizer therefore being a strong choice for this project. They all use the same circuit but have different levels of sensitivity to volume.  A demonstration of the circuits are on the next slide.


The third and final method for making this project is to use transistors. An example of a transistor that I could use is the common but versatile and useful BC547. This would take the input audio signal and amplify it to a higher signal that would be sufficient in driving an LED. Once reaching the adequate signal, the LEDs will turn on similar to an VU meter when transistors and LED are connected in line. However, this would mean that each LED would require its own transistor. This increases not only the bill of materials but also makes the project more bulky as the PCB would be more complicated and filled. Therefore, the project requires a casing large enough to house the entire circuit. 


Hours Spent: 6.25Hrs

## xx/xx/25 - Chosen Method

Hours Spent: 

## xx/xx/25 - Specification

Hours Spent: 


## xx/xx/25 - Researching the history
#### The LED
In 1907, Henry Joseph Round first discovered electroluminescence while working with silicon carbide crystals. His discovery occurred while he was applying an electric current to the crystals, causing him to notice that they emitted light. This discovery was integral to the development of the LED as it paved the way for Nick Holonyak Jr, an American engineer. Holonyak Jr created the first practical LED, emitting a colour on the visible spectrum in 1962. He used a material called gallium arsenide phosphide to produce an LED that emitted visible red light upon applying a current to it. This is an example of a technology push causing the further development of the LED making a commercially and scientifically significant difference to the production of electronic goods. 
#### The Microphone
Emile Berliner was the first to create a practical microphone in 1876. He developed a carbon button microphone that was used in the early models of the bell telephone. The microphone was later developed by Gerhard Sessler and James West at Bell Laboratories in 1962. They created the electret microphone which is now one of the most commonly used microphones today. This was a development from the older condenser microphones. They managed to find a plastic that could hold electricity by itself without an external power supply making it smaller and cheaper thus better and more reliable than the older microphones.

Hours Spent: 

## xx/xx/25 - 1st Iteration of LM3915
To start prototyping my project, I first attempted to breadboard the LM3915 circuit non-cascading and using a potentiometer to create an analogue signal as a substitute for the microphone. On this attempt, however, the circuit didn’t work as expected. After investigating my breadboard further alongside the datasheet for the LM3915, I discovered my mistake. I found that the circuit wasn’t working because in the data sheet, the cathode, which is the positive leg, of the LED was supposed to be connected to the output pins of the LM3915. Then the anode was meant to be connected to the plus volts which is the row where the red wire feeds into. In my breadboard though, I had connected the anode to the output pins and the resistors to the cathode of the LED which were connected to ground. Therefore my circuit failed to work.


Hours Spent:

## xx/xx/25 - 2nd Iteration of LM3915

After correcting the circuit by connecting the anode to the output pins of the LM3915 the circuit still failed. After further examination of the circuit, I noticed that I had connected the resistors for the reference voltage in the same track causing it to short circuit and therefore fail. Furthermore, the LEDs should have be connected to plus volts as well as I had discovered in my first iteration. However, I had forgotten to do this , further contributing to the failure of the circuit.


Hours Spent:

## xx/xx/25 - 3rd Iteration of LM3915

I corrected the mistakes by stretching the resistor to the right and connecting it using wires to the pins and connecting the LEDs to plus volts. This proved successful as the LEDs now turned on when I powered on my circuit. 
However, again, the circuit didn’t work completely as expected. All of the LEDs remained on despite changing the resistance of the potentiometer whereas they should have turned on one by one as I rotated the potentiometer. 

Hours Spent:
