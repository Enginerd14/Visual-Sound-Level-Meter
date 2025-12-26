## 4/11/25 - Researching methods
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

This was not done in one sitting but I combined it for ease of reading :)
Hours Spent: 8.25Hrs

## 9/11/25 - Chosen Method

I have chosen a microphone for the audio input so the device can be used wherever sound is present, rather than relying on a cable connection.

After deep research, for the LED driver, I chose the LM3915 over the PIC and the transitors LM3914 and LM3916 due to its sensitivity and logarithmic scale with increments of 3dB(so 1 LED bar graph covers 30dB) making it perfectly suitable for a sound level meter. However, any of the 3 would work completely fine for this project. You will need 1 IC per 10 LEDs/ 1 LED bar graph.

I also decided to test both the LM386 and the TDA7266 as the audio amp and choose the one that works best.

Finally, to provide the visual output I decided on the LED bar graph which is generally composed of 10 LEDs and has a compact size with an aesthetic appeal but you can also use a number of LEDs instead.

Hours Spent: 2Hrs

## 16/08/25 - Specification





Hours Spent: 


## 10/11/25 - Researching the history
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

Hours Spent: 3.5Hrs

## 10/11/25 - CAD model design

I created a few CAD designs of what the different final outcomes could look like but these were not to scale and were only an illustration of what it could look like. 

Hours Spent: 5.25Hrs

## 13/11/25 - Finding out how the LM3915 works

I studied the datasheet intensely to find out how the circuit works. This is what I found...

The LM3915 is an analogue display driver that takes a input voltage to drive a 10 segment LED bar graph/ 10 LEDs using an internal logarithmic scale which increments by 3dB per step. This is ideal for sound applications as it matches how we perceive loudness.

Below is a list of the pins and their purpose:

Pin 1 and 10-18: These pins connect to the LEDs

Pin 2 and 3: These pins provide power to the IC and complete the circuit

Pin 4 (Ref Low): The bottom of the scale where first LED turns on

Pin 5 (Signal): This pin takes the Input Audio signal

Pin 6 (Ref High): The top of the scale where top LED turns on

Pin 7(Ref Out): Controls LED current changing brightness of the LED

Pin 8(Ref Adj): Sets the reference voltage and controls the sensitivity

Pin 9 (Mode): This controls the sequence of the LEDs, either in DOT mode(one LED turned on sequentially) or BAR mode(LEDs turn on consecutively)

Hours Spent:

## 15/11/25 - 1st Iteration of LM3915
To start prototyping my project, I first attempted to breadboard the LM3915 circuit non-cascading and using a potentiometer to create an analogue signal as a substitute for the microphone. On this attempt, however, the circuit didn’t work as expected. After thoroughly investigating my breadboard further alongside the datasheet for the LM3915, I discovered my mistake. I found that the circuit wasn’t working because in the data sheet, the cathode, which is the positive leg, of the LED was supposed to be connected to the output pins of the LM3915. Then the anode was meant to be connected to the plus volts which is the row where the red wire feeds into. In my breadboard though, I had connected the anode to the output pins and the resistors to the cathode of the LED which were connected to ground. Therefore my circuit failed to work.

<img width="633" height="295" alt="image" src="https://github.com/user-attachments/assets/3a063a26-2a87-4f97-87a9-aab5ce019e4e" />

Hours Spent: 3Hrs

## 16/11/25 - 2nd Iteration of LM3915

After correcting the circuit by connecting the anode to the output pins of the LM3915 the circuit still failed. After further examination of the circuit, I noticed that I had connected the resistors for the reference voltage in the same track causing it to short circuit and therefore fail. Furthermore, the LEDs should have be connected to plus volts as well as I had discovered in my first iteration. However, I had forgotten to do this , further contributing to the failure of the circuit.

<img width="850" height="298" alt="image" src="https://github.com/user-attachments/assets/21b968d2-771d-4772-afe2-7289b123f59a" />

I corrected the mistakes by stretching the resistor to the right and connecting it using wires to the pins and connecting the LEDs to plus volts. This proved successful as the LEDs now turned on when I powered on my circuit.

<img width="618" height="263" alt="image" src="https://github.com/user-attachments/assets/f35494ac-4faf-4d1a-94da-5700a9ef585f" />

However, again, the circuit didn’t work completely as expected. All of the LEDs remained on despite changing the resistance of the potentiometer whereas they should have turned on one by one as I rotated the potentiometer. 

<img width="619" height="259" alt="image" src="https://github.com/user-attachments/assets/0e320b66-aae3-4384-b656-bbc8560e5bc1" />

Hours Spent: 4Hrs

## 17/11/25 - 3rd Iteration of LM3915

For my 4th attempt, I confirmed, using a logic probe, that the potentiometers input was working. Alongside this, I also found that the outputs of the LM3915 chip were held high when they should have been low. Therefore I decided to rewire the LEDs directly to the chip with no resistors as the IC chip already has a network of resistors built in.

<img width="389" height="256" alt="image" src="https://github.com/user-attachments/assets/6f2106e9-8469-4534-944f-61c205afc7af" />

This worked and my circuit performed as expected. As I rotated the potentiometer, the LED lights turned on one by one as the voltage increased. Now, I will need to build an amplifying circuit for the microphone to replace the potentiometer.

https://github.com/user-attachments/assets/2fd9c7aa-02a3-485f-bf35-63f800ede160

Hours Spent: 2.5Hrs

## 18/11/25 - 1st Iteration of LM3915 cascading circuit on Circuit Wizard

I then looked to create a cascading circuit with the LM3915. This is when you combine two chips and two LED bar graphs so that one LED bar graph turns on fully and then the other begins to turn on once the first one is entirely on so it creates a single bar. This was my first attempt on circuit wizard to create a cascading circuit with the LM3915. However, the attempt was unsuccessful. 

<img width="363" height="321" alt="image" src="https://github.com/user-attachments/assets/fc15e040-1131-4ddd-b515-c4d030c1a04f" />
<img width="365" height="213" alt="image" src="https://github.com/user-attachments/assets/04292d4a-1dc0-4c92-be88-5447f8b5f867" />

https://github.com/user-attachments/assets/24a29da8-6dcd-465d-8769-79b624df0bc3

On my second attempt, one LED bar graph remained on for the full time while the other bar graph turned on sequentially.   

<img width="506" height="508" alt="image" src="https://github.com/user-attachments/assets/ada5a91c-f880-4ec9-ba55-8f20fbfa90a8" />

https://github.com/user-attachments/assets/679a3a3f-da81-4daf-b225-d38ebaf53af2

For my third attempt, I followed the LM3915 datasheet for the circuit diagram that is shown on the left. This still did not work as expected. The LEDs on both of the bar graphs remained on fully. 

<img width="621" height="190" alt="image" src="https://github.com/user-attachments/assets/83e2ad63-e6c5-44ee-9280-c3730a360ffb" />
<img width="468" height="292" alt="image" src="https://github.com/user-attachments/assets/ba3f25e4-1ea3-4f40-ad03-81a52efe4362" />

https://github.com/user-attachments/assets/b65bbbcb-cd1e-4f91-b2d6-47c6a777f7b1

On my fourth try, I used another method of cascading the LM3915 from the datasheet. This worked better than before but still was not perfected as there was an overlap of LEDs between the bar graphs.

<img width="465" height="290" alt="image" src="https://github.com/user-attachments/assets/7a990614-e487-4bde-953b-d485cd14c018" />
<img width="561" height="239" alt="image" src="https://github.com/user-attachments/assets/585ea9c7-710a-473a-b900-d68258ee64fc" />

https://github.com/user-attachments/assets/2ea70734-821a-4d35-a42e-a8c377013a76

After many failed attempts, I changed my schematic to a another one as shown on the right. After connecting this up, it worked perfectly as all the LEDs turned on for the first bar graph before they turned on for the second bar.  I also fixed the order in which they turned on.

<img width="434" height="295" alt="image" src="https://github.com/user-attachments/assets/0dfb5dcf-75ae-4591-b96b-169139d9e0d6" />
<img width="515" height="221" alt="image" src="https://github.com/user-attachments/assets/eceded9c-47aa-46ed-87f0-f092bbac3b84" />

https://github.com/user-attachments/assets/6c0bd98b-783c-4b2b-b63f-a9d15f8ed98b

Hours Spent: 6.5Hrs

## 20/11/25 - 1st Iteration of LM3915 cascading circuit 

Using my working circuit wizard schematic, I breadboarded the cascading circuit and used a 1K potentiometer to act as the input signal which will be replaced by the microphone circuit amplified by the LM386 amplifier that I had breadboarded earlier. Upon changing the resistance of the potentiometer, the LEDs worked as expected and they turned on sequentially. This created the 20 LED scale that I will use in my project.

https://github.com/user-attachments/assets/0518f570-b7a8-470e-89ca-3e4b90909c6f

Hours Spent: 2.5Hrs

## 21/11/25 - 1st Iteration LM386

To create the amplifying circuit for the microphone, I had two component options : the LM386 and the TDA7266. I chose to begin with the LM386 Op-amp which was the simpler but in turn weaker amplifier. This was my first attempt at creating the amplifier circuit with the LM386 to amplify the microphone signal and input it into as the analogue signal for the LM3915 instead of the current potentiometer. However my attempt was not entirely successful as the circuit was too sensitive and some LEDs remained on even when there was no audible sound. One of the reasons that this could be happening is because of the constant but quiet 50Hz of Alternating current. The fix for this is too include some way of altering the sensitivity of the microphone signal that is being amplified. A method of doing this would be to include a potentiometer between the input signal pin in the amplifier chip and the microphone.

<img width="320" height="270" alt="image" src="https://github.com/user-attachments/assets/3242dd92-e2e7-44d5-b943-4d135e362acf" />
<img width="410" height="236" alt="image" src="https://github.com/user-attachments/assets/0b2e51fb-70b4-4be8-9426-c3a4010e673b" />

Hours Spent: 3Hrs

## 22/11/25 - 2nd Iteration of LM386

For the second attempt, I used a 10K potentiometer between pin 3, the analogue input signal for the amplifying chip, and the microphone, as seen in the circuit diagram below, allowing me to adjust the sensitivity of the microphone. This worked effectively and meant the LEDs remained off when there was no audible sound that could be heard by the human ear. 

<img width="412" height="356" alt="image" src="https://github.com/user-attachments/assets/1eeb9ad2-73d4-45e2-84d8-760b4151d370" />
<img width="590" height="231" alt="image" src="https://github.com/user-attachments/assets/e509985b-2aa8-4cdc-b169-d272342992e7" />

Hours Spent: 2Hrs

## 24/11/25 - 1st Iteration of LM3915 and LM386

I connected my LM386 amplifier circuit to the analogue input signal of the LM3915 which is pin 5. On doing this, the LEDs turned on as the microphone picked up sound. However, the LEDs turned on simultaneously as the microphone detected sound. They should have turned on one by one as volume increases and then turn off one by one as it decreases.

https://github.com/user-attachments/assets/eb3f0788-d1ea-40c4-9e93-2418777b1dde

As expected, the LM386 amplifier was not strong enough to amplify the signal to a high enough range to power the LEDs. Therefore, I switched to a much stronger amplifier: the TDA7266. The TDA7266 is meant to amplify the signal from the microphone to a signal high enough for speakers. Thus, it should be more than sufficient for powering the range of the LEDs. 

<img width="287" height="290" alt="image" src="https://github.com/user-attachments/assets/24317ad5-b548-41f2-be8a-bf2fa25c2812" />

Hours Spent: 3.5hrs

## 25/11/25 - Researching TDA7266

To create the TDA7266, I looked into the datasheet to see what I needed to connect and how it worked before prototyping.

Pin 1(OUT1+): Output pin for the red (positive) wire of the speaker. This is the one we will join to the input pin of the LM3915
Pin 2(OUT1-): Output pin for the black (negative) wire of the speaker. This is not required for the LM3915.
Pin 3 and 13(VCC): Power supply (plus volts) connected with two capacitors
Pin 4(IN1): Input signal from microphone with 0.22 microfarads capacitor(or a value close enough)
Pin 7(ST-BY): This controls whether the amplifier is active or in Standby by using a voltage threshold
Pin 9(S-GND): Power supply (0V/ ground)
Circuit wizard didn't have this component available either so instead I breadboarded it directly and have attached an image of my working breadboard as well as the circuit diagram provided in the datasheet.

To combine the microphone with the TDA7266, the microphone requires its own circuit. This consists of a 1.5K resistor connected from the ground voltage to the ground pin of the microphone (shown by the metal connecting the pin to the outer casing of the microphone). The positive pin connects to pin 4 of the TDA7266.

Hours Spent:3Hrs

## 26/11/25 - 1st Iteration of TDA7266

I breadboarded the TDA7266 circuit and I used the speaker to test whether the microphone and my amplifier circuit were working. Once I powered my circuit, I should have heard a click from the speaker when the microphone picked up on some sound but this did not occur. Upon further inspection, it was clear that the pins of the amplifier chip were not in the breadboard. This was due to the awkward shape of the pins. To fix this I used a pair of pliers to bend and force the pins into the breadboard. Once the pins were fitted in, I again powered the circuit and used the speaker to test the circuit. This time I could clearly hear the speaker when the microphone picked up sound.

<img width="443" height="358" alt="image" src="https://github.com/user-attachments/assets/95cf609a-b55c-468e-abf9-08a61deb40c5" />
<img width="251" height="499" alt="image" src="https://github.com/user-attachments/assets/d5f657b4-1f86-4e0c-a022-97417393c75f" />
<img width="263" height="495" alt="image" src="https://github.com/user-attachments/assets/da23a178-ba4e-47eb-8679-33a1c240f8ed" />

Hours Spent: 3.5Hrs

## 28/11/25 - 1st Iteration of LM3915 and TDA7266

With a working microphone amplifying circuit using the TDA7266, I then looked at combining it with the LM3915. I connected the output pin from the TDA7266 to the signal input pin in my LM3915 cascading circuit. After powering on the entire circuit, I tested the combination. When the microphone picked up sound, the speaker still outputted this sound, ensuring that the TDA7266 was working as expected. However, despite connecting the circuits together, the LM3915 remained on fully, regardless of the microphone signal. 

https://github.com/user-attachments/assets/f45f54c8-7b37-46e5-acf5-42d902fe9c2a

Both circuits worked as expected individually, but when combining the two, they failed to produce the desired outcome. My first thought was that the TDA7266 used two output pins as one was meant for the black speaker wire( zero volts)  and the other for the red speaker wire (plus volts) but I only used one wire going from the plus volts output pin to the signal pin. However, this should not affect the circuit as it is only for grounding the speaker. Instead, I added a 100k resistor connecting the signal pin to ground but still allowing current to flow. This provided a reference for the LM3915 to sense voltage changes(from the microphone) from ground.

https://github.com/user-attachments/assets/a47a75ed-9d45-499d-acfb-030a4748a6d8

Hours Spent: 4hrs

## 29/11/25 - Designing the PCB

Now that I had a working breadboard, I looked at making a Printed Circuit Board to house the components for my project. I have decided to make 3 PCBs for the 3 different parts of my project. One for the TDA7266 amplifying circuit with the microphone. One for the LM3915 IC. And one for the LED bar graphs. I started with the LM3915 PCB. On the right is my first attempt. When I tested the PCB, I found that the top LED bar graph turned on before the bottom one did which is the opposite of what was expected. 

https://github.com/user-attachments/assets/6355bcd3-a77e-4e1f-9847-a17f8e9ea8c8

To fix the mistake, I switched the circuitry for the chips around. This time when I powered my circuit, it worked perfectly and as expected. All of the LEDs on the bottom bar graph turned on sequentially and then all of the second LED bar graph turned on in the same way. 

https://github.com/user-attachments/assets/0eb5199e-d0a9-4525-8dbc-cb6500f1c272

I now had to create the PCB to have the LM3915 cascading circuit 3 times. I connected two PCB tracks from each end of the circuit. The one at the top going to all the circuits connected the plus volts. The one on the bottom connected to ground. This meant I only needed 2 wires from the battery pack to the tracks at either end, instead of using 6 wires going to each chip individually. 

https://github.com/user-attachments/assets/5b7bbdbe-f083-471c-ab66-015706b1e16d

Hours Spent: 5Hrs

## 30/11/25 - Producing the PCB

First, I printed my circuit onto an acetate sheet. This will be used to make my circuit tracks on the pcb. 

<img width="248" height="225" alt="image" src="https://github.com/user-attachments/assets/fba63467-295a-4f0d-a801-f597d904dc86" />

Then I used the guillotine to cut the copper plated board into the correct size for the PCB.

<img width="313" height="200" alt="image" src="https://github.com/user-attachments/assets/d087cf19-3176-4c4b-80f3-5459cde76cd5" />

I then placed the acetate sheet on the copper side of the PCB and used the UV exposure box to soften the photoresist layer on the copper board.

<img width="305" height="138" alt="image" src="https://github.com/user-attachments/assets/c1c4f265-8922-47c3-bb03-ba6d132fb32f" />

Then using developer solution, I developed the tracks and used an acid etch tank to remove the excess copper.

I then had a PCB ready. I used a multimeter and used continuity mode to ensure the tracks were all connected.

WHile drilling holes in my PCB, I  realised that I forgot the copper pads where I would solder wires and connect my other PCB with the LEDs, shown by the red circles below. 

<img width="542" height="339" alt="image" src="https://github.com/user-attachments/assets/1fe9dbd1-5f26-4630-b0ba-b35d97625465" />

Hours Spent: 5.5hrs

## 1/12/25

I added in the pads and remade my PCB. Again, using the multimeters' continuity mode, I tested whether the tracks were all connected. I then began drilling the holes on the PCB which took some time considering there were over 200 holes which I had to hand drill! I then began soldering some of my components.

Hours Spent: 5hrs

## 2/12/25

I finished soldering the components and all of the wires which was a LOT! 



Hours Spent: 4Hrs

## 4/12/25 - Designing the LED PCB

I began designing the PCB for the LED bar graphs to sit on the top of all of the PCBs. 

Hours Spent: 2.5Hrs

## 6/12/25 - Producing the LED PCB

I produced the PCB and once again tested the continutity of the tracks using a multimeter. Everything looked good so I began drilling the 360 holes with a hand drill :(

Hours Spent: 5Hrs

## 7/12/25 - Testing the PCBs

I combined the LED bar graph and the control PCB. 

It didn't work :( 

I tested the LED PCB which was working perfectly so it has to be the control PCB. I used a logic probe to test the control PCB and noticed a lot of mistakes. I required a lot of wire jumpers and also forgot to have a track connecting ground for all f the different parts of the circuit. I had to redesign and remake it. At least I don't have to drill 360 holes this time, only 200 :(

Hours Spent: 3.5hrs

## 8/12/25 - Redesigning the main PCB

I decided to completely redesign my PCB and start from scratch. This was extremely difficult and time consuming to make sure all the tracks were connected and did not cross but also keep it at a acceptable size. But in the end I managed to simplify it and remove all of my wire jumpers and also reduce the size significantly. ( It now fits within the palm of my hand!!!)

Hours Spent: 4Hrs

## 9/12/25 - Producing the redesigned main PCB

Once more, I produced my PCB and tested the continuity using a multimeter. Once ensuring all tracks were connected, I promptly began the drilling. 

Hours Spent: 3.5Hrs

## 10/12/25 - Soldering my PCB

I began and managed to complete all of the soldering of my PCB. I decided not to solder every wire this time, only a couple for testing first. 

I connected both PCBs. I connected the power wires to my breadboard. And then I switched on my power supply......

And IT WORKED!!!!

Hours Spent: 4hrs

## 12/12/25 - TDA7266 PCB

I began designing my final PCB: the TDA7266 amplifier with the microphone. This was difficult as my working protoype was slighlty different to the schematic on the datasheet, but I managed in the end using a multimeter to test the values of all my components in my PCB. 

I can't wait to finish it and I'm so close but unfortunately, this as far as I can get for now with this project as I have exams coming up :( 

Hours Spent: 3Hrs



