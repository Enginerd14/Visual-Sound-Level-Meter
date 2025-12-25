## xx/xx/25 - Researching methods
I looked into the various methods of making a VU meter. One of the methods I discovered was using a Programmable Integrated Circuit (PIC)  such as the Genie 20. The Genie 20 has seven output pins allowing it to power seven LEDs as the visual indicator for the VU meter. Each LED would require a 220Ω adding to the bill of materials. Using a programmable circuit, I can use a flowchart to control the chip and control which LEDs turn on depending on the signal level. I used circuit wizard to create both the circuit and the flowchart. Screenshots can be found below. In the flowchart, the analogue signal box checks if the input signal matches the signal range that I have provided. The range goes from 0 to 255 and I split this equally to determine which LEDs will turn on. In my circuit, I used an LDR for visual representation as Circuit wizard does not have a microphone as one of the available components so the LDR acts as the analogue signal that would be coming from the microphone. I can then program the flowchart in multiple ways: I could either have the LEDs move from the middle going outwards as the volume increases or have them move from bottom to top instead. This makes this method a very flexible and customisable circuit. 

<img width="531" height="235" alt="image" src="https://github.com/user-attachments/assets/05dbb6f9-f467-4926-9757-a3f85428fc5c" />
<img width="412" height="260" alt="image" src="https://github.com/user-attachments/assets/fb74f05c-16f3-4d34-84a1-c21c48ac74a5" />


I found another way of making a VU meter. This can be done through a LED bar graph and a LM39_ _ IC. The LED bar graph is composed of 10 LEDs stacked on top of each other to create a visual scale using light and colour. Most LEDs require resistors and this is the same for the LED bar graph. However, the LM39_ _,which is bar graph driver IC that is complementary to the LED bar graph, has a built in network of resistors within the chip itself. Thus, I will not require ten extra LEDs for the LEDs, reducing the bill of materials for my project.  The LM39_ _ driver comes in 3 variations: LM3914, LM3915 and LM3916. The LM3914 is a linear display used mainly in alarms and voltmeters. The LM3915 is a logarithmic display incremented by 3dB to turn each LED on after the previous one making it a good contender for a VU meter. The LM3916 is designed specifically for a VU meter which is a volume unit meter or also known as an audio visualizer therefore being a strong choice for this project. They all use the same circuit but have different levels of sensitivity to volume.  A demonstration of the circuits are on the next slide.

<img width="445" height="307" alt="image" src="https://github.com/user-attachments/assets/7c8adf9c-64ce-4ce9-8a37-60e7ee32103e" />
<img width="308" height="364" alt="image" src="https://github.com/user-attachments/assets/2b02a44c-2d47-43b9-892e-10e685477348" />
<img width="271" height="362" alt="image" src="https://github.com/user-attachments/assets/25c81673-db5a-490a-87c1-160ab57af953" />


The third and final method for making this project is to use transistors. An example of a transistor that I could use is the common but versatile and useful BC547. This would take the input audio signal and amplify it to a higher signal that would be sufficient in driving an LED. Once reaching the adequate signal, the LEDs will turn on similar to an VU meter when transistors and LED are connected in line. However, this would mean that each LED would require its own transistor. This increases not only the bill of materials but also makes the project more bulky as the PCB would be more complicated and filled. Therefore, the project requires a casing large enough to house the entire circuit. 

<img width="420" height="301" alt="image" src="https://github.com/user-attachments/assets/2149f0af-708e-4deb-b423-6399565228e8" />
<img width="423" height="334" alt="image" src="https://github.com/user-attachments/assets/ea18e501-9e5a-484e-a2cd-e018750451b7" />


Hours Spent: 6.25Hrs

## xx/xx/25 - Chosen Method

Hours Spent: 

## xx/xx/25 - Specification

Hours Spent: 


## xx/xx/25 - Researching the history
#### The LED
In 1907, Henry Joseph Round first discovered electroluminescence while working with silicon carbide crystals. His discovery occurred while he was applying an electric current to the crystals, causing him to notice that they emitted light. This discovery was integral to the development of the LED as it paved the way for Nick Holonyak Jr, an American engineer. Holonyak Jr created the first practical LED, emitting a colour on the visible spectrum in 1962. He used a material called gallium arsenide phosphide to produce an LED that emitted visible red light upon applying a current to it. This is an example of a technology push causing the further development of the LED making a commercially and scientifically significant difference to the production of electronic goods. 

<img width="371" height="255" alt="image" src="https://github.com/user-attachments/assets/a73d49a2-d391-405c-b53e-f375551a7e70" />
<img width="382" height="255" alt="image" src="https://github.com/user-attachments/assets/0e252731-2a37-42ad-b791-03fa62128778" />
<img width="314" height="252" alt="image" src="https://github.com/user-attachments/assets/9288c522-c265-4566-9ba0-554086693a0c" />

#### The Microphone
Emile Berliner was the first to create a practical microphone in 1876. He developed a carbon button microphone that was used in the early models of the bell telephone. The microphone was later developed by Gerhard Sessler and James West at Bell Laboratories in 1962. They created the electret microphone which is now one of the most commonly used microphones today. This was a development from the older condenser microphones. They managed to find a plastic that could hold electricity by itself without an external power supply making it smaller and cheaper thus better and more reliable than the older microphones.

<img width="206" height="306" alt="image" src="https://github.com/user-attachments/assets/cbf14e06-c212-4499-b99f-095b251643e8" />
<img width="402" height="230" alt="image" src="https://github.com/user-attachments/assets/63685491-403a-4ca8-847a-b4f7b131fff7" />
<img width="268" height="232" alt="image" src="https://github.com/user-attachments/assets/a5d5b0b8-f7b5-4393-80ea-89cd31daa00f" />

Hours Spent: 

## xx/xx/25 - 1st Iteration of LM3915
To start prototyping my project, I first attempted to breadboard the LM3915 circuit non-cascading and using a potentiometer to create an analogue signal as a substitute for the microphone. On this attempt, however, the circuit didn’t work as expected. After investigating my breadboard further alongside the datasheet for the LM3915, I discovered my mistake. I found that the circuit wasn’t working because in the data sheet, the cathode, which is the positive leg, of the LED was supposed to be connected to the output pins of the LM3915. Then the anode was meant to be connected to the plus volts which is the row where the red wire feeds into. In my breadboard though, I had connected the anode to the output pins and the resistors to the cathode of the LED which were connected to ground. Therefore my circuit failed to work.

<img width="633" height="295" alt="image" src="https://github.com/user-attachments/assets/3a063a26-2a87-4f97-87a9-aab5ce019e4e" />


Hours Spent:

## xx/xx/25 - 2nd Iteration of LM3915

After correcting the circuit by connecting the anode to the output pins of the LM3915 the circuit still failed. After further examination of the circuit, I noticed that I had connected the resistors for the reference voltage in the same track causing it to short circuit and therefore fail. Furthermore, the LEDs should have be connected to plus volts as well as I had discovered in my first iteration. However, I had forgotten to do this , further contributing to the failure of the circuit.

<img width="850" height="298" alt="image" src="https://github.com/user-attachments/assets/21b968d2-771d-4772-afe2-7289b123f59a" />


Hours Spent:

## xx/xx/25 - 3rd Iteration of LM3915

I corrected the mistakes by stretching the resistor to the right and connecting it using wires to the pins and connecting the LEDs to plus volts. This proved successful as the LEDs now turned on when I powered on my circuit.

<img width="618" height="263" alt="image" src="https://github.com/user-attachments/assets/f35494ac-4faf-4d1a-94da-5700a9ef585f" />

However, again, the circuit didn’t work completely as expected. All of the LEDs remained on despite changing the resistance of the potentiometer whereas they should have turned on one by one as I rotated the potentiometer. 

<img width="619" height="259" alt="image" src="https://github.com/user-attachments/assets/0e320b66-aae3-4384-b656-bbc8560e5bc1" />

Hours Spent:

## xx/xx/25 - 4th Iteration of LM3915

For my 4th attempt, I confirmed, using a logic probe, that the potentiometers input was working. Alongside this, I also found that the outputs of the LM3915 chip were held high when they should have been low. Therefore I decided to rewire the LEDs directly to the chip with no resistors as the IC chip already has a network of resistors built in.

<img width="389" height="256" alt="image" src="https://github.com/user-attachments/assets/6f2106e9-8469-4534-944f-61c205afc7af" />

This worked and my circuit performed as expected. As I rotated the potentiometer, the LED lights turned on one by one as the voltage increased. Now, I will need to build an amplifying circuit for the microphone to replace the potentiometer.

Hours Spent:


## xx/xx/25 - 1st Iteration of LM3915 cascading circuit on Circuit Wizard

I then looked to create a cascading circuit with the LM3915. This is when you combine two chips and two LED bar graphs so that one LED bar graph turns on fully and then the other begins to turn on once the first one is entirely on so it creates a single bar. This was my first attempt on circuit wizard to create a cascading circuit with the LM3915. However, the attempt was unsuccessful. 

On my second attempt, one LED bar graph remained on for the full time while the other bar graph turned on sequentially.   

For my third attempt, I followed the LM3915 datasheet for the circuit diagram that is shown on the left. This still did not work as expected. The LEDs on both of the bar graphs remained on fully. 

On my fourth try, I used another method of cascading the LM3915 from the datasheet. This worked better than before but still was not perfected as there was an overlap of LEDs between the bar graphs.

After many failed attempts, I changed my schematic to a another one as shown on the right. After connecting this up, it worked perfectly as all the LEDs turned on for the first bar graph before they turned on for the second bar.  I also fixed the order in which they turned on.

Hours Spent:

## xx/xx/25 - 1st Iteration of LM3915 cascading circuit 

Using my working circuit wizard schematic, I breadboarded the cascading circuit and used a 1K potentiometer to act as the input signal which will be replaced by the microphone circuit amplified by the LM386 amplifier that I had breadboarded earlier. Upon changing the resistance of the potentiometer, the LEDs worked as expected and they turned on sequentially. This created the 20 LED scale that I will use in my project.

## xx/xx/25 - 1st Iteration LM386

To create the amplifying circuit for the microphone, I had two component options : the LM386 and the TDA7266. I chose to begin with the LM386 Op-amp which was the simpler but in turn weaker amplifier. This was my first attempt at creating the amplifier circuit with the LM386 to amplify the microphone signal and input it into as the analogue signal for the LM3915 instead of the current potentiometer. However my attempt was not entirely successful as the circuit was too sensitive and some LEDs remained on even when there was no audible sound. One of the reasons that this could be happening is because of the constant but quiet 50Hz of Alternating current. The fix for this is too include some way of altering the sensitivity of the microphone signal that is being amplified. A method of doing this would be to include a potentiometer between the input signal pin in the amplifier chip and the microphone.

<img width="320" height="270" alt="image" src="https://github.com/user-attachments/assets/3242dd92-e2e7-44d5-b943-4d135e362acf" />
<img width="410" height="236" alt="image" src="https://github.com/user-attachments/assets/0b2e51fb-70b4-4be8-9426-c3a4010e673b" />

Hours Spent:

## xx/xx/25 - 2nd Iteration of LM386

For the second attempt, I used a 10K potentiometer between pin 3, the analogue input signal for the amplifying chip, and the microphone, as seen in the circuit diagram below, allowing me to adjust the sensitivity of the microphone. This worked effectively and meant the LEDs remained off when there was no audible sound that could be heard by the human ear. 

<img width="412" height="356" alt="image" src="https://github.com/user-attachments/assets/1eeb9ad2-73d4-45e2-84d8-760b4151d370" />
<img width="590" height="231" alt="image" src="https://github.com/user-attachments/assets/e509985b-2aa8-4cdc-b169-d272342992e7" />

Hours Spent:

## xx/xx/25 - 1st Iteration of LM3915 and LM386

I connected my LM386 amplifier circuit to the analogue input signal of the LM3915 which is pin 5. On doing this, the LEDs turned on as the microphone picked up sound. However, the LEDs turned on simultaneously as the microphone detected sound. They should have turned on one by one as volume increases and then turn off one by one as it decreases.

https://github.com/user-attachments/assets/eb3f0788-d1ea-40c4-9e93-2418777b1dde

As expected, the LM386 amplifier was not strong enough to amplify the signal to a high enough range to power the LEDs. Therefore, I switched to a much stronger amplifier: the TDA7266. The TDA7266 is meant to amplify the signal from the microphone to a signal high enough for speakers. Thus, it should be more than sufficient for powering the range of the LEDs. 

<img width="287" height="290" alt="image" src="https://github.com/user-attachments/assets/24317ad5-b548-41f2-be8a-bf2fa25c2812" />

Hours Spent:

## xx/xx/25 - 1st Iteration of TDA7266

I breadboarded the TDA7266 circuit and I used the speaker to test whether the microphone and my amplifier circuit were working. Once I powered my circuit, I should have heard a click from the speaker when the microphone picked up on some sound but this did not occur. Upon further inspection, it was clear that the pins of the amplifier chip were not in the breadboard. This was due to the awkward shape of the pins. To fix this I used a pair of pliers to bend and force the pins into the breadboard. Once the pins were fitted in, I again powered the circuit and used the speaker to test the circuit. This time I could clearly hear the speaker when the microphone picked up sound.

<img width="443" height="358" alt="image" src="https://github.com/user-attachments/assets/95cf609a-b55c-468e-abf9-08a61deb40c5" />
<img width="251" height="499" alt="image" src="https://github.com/user-attachments/assets/d5f657b4-1f86-4e0c-a022-97417393c75f" />
<img width="263" height="495" alt="image" src="https://github.com/user-attachments/assets/da23a178-ba4e-47eb-8679-33a1c240f8ed" />

Hours Spent:

## xx/xx/25 - 1st Iteration of LM3915 and TDA7266

With a working microphone amplifying circuit using the TDA7266, I then looked at combining it with the LM3915. I connected the output pin from the TDA7266 to the signal input pin in my LM3915 cascading circuit. After powering on the entire circuit, I tested the combination. When the microphone picked up sound, the speaker still outputted this sound, ensuring that the TDA7266 was working as expected. However, despite connecting the circuits together, the LM3915 remained on fully, regardless of the microphone signal. 

https://github.com/user-attachments/assets/f45f54c8-7b37-46e5-acf5-42d902fe9c2a

Both circuits worked as expected individually, but when combining the two, they failed to produce the desired outcome. My first thought was that the TDA7266 used two output pins as one was meant for the black speaker wire( zero volts)  and the other for the red speaker wire (plus volts) but I only used one wire going from the plus volts output pin to the signal pin. However, this should not affect the circuit as it is only for grounding the speaker. Instead, I added a 100k resistor connecting the signal pin to ground but still allowing current to flow. This provided a reference for the LM3915 to sense voltage changes(from the microphone) from ground.

https://github.com/user-attachments/assets/a47a75ed-9d45-499d-acfb-030a4748a6d8

Hours Spent:

## xx/xx/25 - Designing the PCB

Now that I had a working breadboard, I looked at making a Printed Circuit Board to house the components for my project. I have decided to make 3 PCBs for the 3 different parts of my project. One for the TDA7266 amplifying circuit with the microphone. One for the LM3915 IC. And one for the LED bar graphs. I started with the LM3915 PCB. On the right is my first attempt. When I tested the PCB, I found that the top LED bar graph turned on before the bottom one did which is the opposite of what was expected. 

https://github.com/user-attachments/assets/6355bcd3-a77e-4e1f-9847-a17f8e9ea8c8

To fix the mistake, I switched the circuitry for the chips around. This time when I powered my circuit, it worked perfectly and as expected. All of the LEDs on the bottom bar graph turned on sequentially and then all of the second LED bar graph turned on in the same way. 

https://github.com/user-attachments/assets/0eb5199e-d0a9-4525-8dbc-cb6500f1c272

I now had to create the PCB to have the LM3915 cascading circuit 3 times. I connected two PCB tracks from each end of the circuit. The one at the top going to all the circuits connected the plus volts. The one on the bottom connected to ground. This meant I only needed 2 wires from the battery pack to the tracks at either end, instead of using 6 wires going to each chip individually. 

https://github.com/user-attachments/assets/5b7bbdbe-f083-471c-ab66-015706b1e16d

Hours Spent:
