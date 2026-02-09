## 4/12/25 - Researching methods
I looked into the various methods of making a VU meter. One of the methods I discovered was using a Programmable Integrated Circuit (PIC)  such as the Genie 20. The Genie 20 has seven output pins allowing it to power seven LEDs as the visual indicator for the VU meter. Each LED would require a 220Ω adding to the bill of materials. Using a programmable circuit, I can use a flowchart to control the chip and control which LEDs turn on depending on the signal level. I used circuit wizard to create both the circuit and the flowchart. Screenshots can be found below. In the flowchart, the analogue signal box checks if the input signal matches the signal range that I have provided. The range goes from 0 to 255 and I split this equally to determine which LEDs will turn on. In my circuit, I used an LDR for visual representation as Circuit wizard does not have a microphone as one of the available components so the LDR acts as the analogue signal that would be coming from the microphone. I can then program the flowchart in multiple ways: I could either have the LEDs move from the middle going outwards as the volume increases or have them move from bottom to top instead. This makes this method a very flexible and customisable circuit. 

<img width="531" height="235" alt="image" src="https://github.com/user-attachments/assets/05dbb6f9-f467-4926-9757-a3f85428fc5c" />
<img width="412" height="260" alt="image" src="https://github.com/user-attachments/assets/fb74f05c-16f3-4d34-84a1-c21c48ac74a5" />

Hours Spent: 1.5hrs

## 5/12/25 - Researching methods
I found another way of making a VU meter. This can be done through a LED bar graph and a LM39_ _ IC. The LED bar graph is composed of 10 LEDs stacked on top of each other to create a visual scale using light and colour. Most LEDs require resistors and this is the same for the LED bar graph. However, the LM39_ _,which is bar graph driver IC that is complementary to the LED bar graph, has a built in network of resistors within the chip itself. Thus, I will not require ten extra LEDs for the LEDs, reducing the bill of materials for my project.  The LM39_ _ driver comes in 3 variations: LM3914, LM3915 and LM3916. The LM3914 is a linear display used mainly in alarms and voltmeters. The LM3915 is a logarithmic display incremented by 3dB to turn each LED on after the previous one making it a good contender for a VU meter. The LM3916 is designed specifically for a VU meter which is a volume unit meter or also known as an audio visualizer therefore being a strong choice for this project. They all use the same circuit but have different levels of sensitivity to volume.  A demonstration of the circuits are on the next slide.

<img width="445" height="307" alt="image" src="https://github.com/user-attachments/assets/7c8adf9c-64ce-4ce9-8a37-60e7ee32103e" />
<img width="308" height="364" alt="image" src="https://github.com/user-attachments/assets/2b02a44c-2d47-43b9-892e-10e685477348" />
<img width="271" height="362" alt="image" src="https://github.com/user-attachments/assets/25c81673-db5a-490a-87c1-160ab57af953" />

Hours Spent: 2Hrs

## 7/12/25 - Researching methods

The third and final method for making this project is to use transistors. An example of a transistor that I could use is the common but versatile and useful BC547. This would take the input audio signal and amplify it to a higher signal that would be sufficient in driving an LED. Once reaching the adequate signal, the LEDs will turn on similar to an VU meter when transistors and LED are connected in line. However, this would mean that each LED would require its own transistor. This increases not only the bill of materials but also makes the project more bulky as the PCB would be more complicated and filled. Therefore, the project requires a casing large enough to house the entire circuit. 

<img width="420" height="301" alt="image" src="https://github.com/user-attachments/assets/2149f0af-708e-4deb-b423-6399565228e8" />
<img width="423" height="334" alt="image" src="https://github.com/user-attachments/assets/ea18e501-9e5a-484e-a2cd-e018750451b7" />
<img width="560" height="219" alt="image" src="https://github.com/user-attachments/assets/03fca261-90d7-4a37-9a43-bebe36b46675" />
<img width="352" height="248" alt="image" src="https://github.com/user-attachments/assets/9df71e3f-a44a-4c99-9e98-81c5fc5fcf61" />

Hours Spent: 1.5Hrs

## 9/12/25 - Chosen Method

I have chosen a microphone for the audio input so the device can be used wherever sound is present, rather than relying on a cable connection.

After deep research, for the LED driver, I chose the LM3915 over the PIC and the transitors LM3914 and LM3916 due to its sensitivity and logarithmic scale with increments of 3dB(so 1 LED bar graph covers 30dB) making it perfectly suitable for a sound level meter. However, any of the 3 would work completely fine for this project. You will need 1 IC per 10 LEDs/ 1 LED bar graph.

I also decided to test both the LM386 and the TDA7266 as the audio amp and choose the one that works best.

Finally, to provide the visual output I decided on the LED bar graph which is generally composed of 10 LEDs and has a compact size with an aesthetic appeal but you can also use a number of LEDs instead.

I created a specification of what features I wanted in my project.

1) Appealing casing/ components 
2) Large range of LEDs that turn on at a different volume range
3) Size - No smaller than (H)50mm x (L)60mm x (W)30mm,  No bigger than (H)70mm x (L)80mm x (W)40mm
4) Sensitive microphone
5) Bright colours
6) Using LED bar graph
7) Use batteries for portability and maintain small size
8) Minimalistic design
9) Durable, appealing,  High quality materials
10) Opening at back for easy access to circuit allowing for replacing batteries and fixing future problems

Hours Spent: 1Hrs

## 10/12/25 - CAD model design

I created a few CAD designs of what the different final outcomes could look like but these were not to scale and were only an illustration of what it could look like. I used a tutorial to find out how to make the control knob and I think it turned out really quite cool!!!

<img width="685" height="698" alt="image" src="https://github.com/user-attachments/assets/5ade1730-6a54-4ca2-b53a-5e69966d9cb6" />
<img width="488" height="270" alt="image" src="https://github.com/user-attachments/assets/84079117-028f-43c2-a879-cd047191312b" />


Hours Spent: 2.5Hrs

## 13/12/25 - Finding out how the LM3915 works

I studied the datasheet intensely to find out how the circuit works. There was a LOT of information on there but I think this is all of the most important info...

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

Hours Spent: 2Hrs

## 15/12/25 - 1st Iteration of LM3915
To start prototyping my project, I first attempted to breadboard the LM3915 circuit non-cascading and using a potentiometer to create an analogue signal as a substitute for the microphone. On this attempt, however, the circuit didn’t work as expected. After thoroughly investigating my breadboard fora an hour comparing each connection to the datasheet for the LM3915 and the explanation, I discovered my mistake. I found that the circuit wasn’t working because in the data sheet, the cathode, which is the positive leg, of the LED was supposed to be connected to the output pins of the LM3915. Then the anode was meant to be connected to the plus volts which is the row where the red wire feeds into. In my breadboard though, I had connected the anode to the output pins and the resistors to the cathode of the LED which were connected to ground. Therefore my circuit failed to work.

<img width="633" height="295" alt="image" src="https://github.com/user-attachments/assets/3a063a26-2a87-4f97-87a9-aab5ce019e4e" />

Hours Spent: 1.5Hrs

## 16/11/25 - 2nd Iteration of LM3915

After correcting the circuit by connecting the anode to the output pins of the LM3915 the circuit still failed. After further examination of the circuit, I noticed that I had connected the resistors for the reference voltage in the same track causing it to short circuit and therefore fail. Furthermore, the LEDs should have be connected to plus volts as well as I had discovered in my first iteration. However, I had forgotten to do this , further contributing to the failure of the circuit.

<img width="850" height="298" alt="image" src="https://github.com/user-attachments/assets/21b968d2-771d-4772-afe2-7289b123f59a" />

I corrected the mistakes by stretching the resistor to the right and connecting it using wires to the pins and connecting the LEDs to plus volts. This proved successful as the LEDs now turned on when I powered on my circuit.

<img width="618" height="263" alt="image" src="https://github.com/user-attachments/assets/f35494ac-4faf-4d1a-94da-5700a9ef585f" />

However, again, the circuit didn’t work completely as expected. All of the LEDs remained on despite changing the resistance of the potentiometer whereas they should have turned on one by one as I rotated the potentiometer. 

<img width="619" height="259" alt="image" src="https://github.com/user-attachments/assets/0e320b66-aae3-4384-b656-bbc8560e5bc1" />

Hours Spent: 2Hrs

## 17/12/25 - 3rd Iteration of LM3915

For my 4th attempt, I confirmed, using a logic probe, that the potentiometers input was working. Alongside this, I also found that the outputs of the LM3915 chip were held high when they should have been low. Therefore I decided to rewire the LEDs directly to the chip with no resistors as after reading the datsheet properly, I realised that the IC chip already has a network of resistors built in.

<img width="389" height="256" alt="image" src="https://github.com/user-attachments/assets/6f2106e9-8469-4534-944f-61c205afc7af" />

This worked and my circuit performed as expected. As I rotated the potentiometer, the LED lights turned on one by one as the voltage increased. Now, I will need to build an amplifying circuit for the microphone to replace the potentiometer.

https://github.com/user-attachments/assets/2fd9c7aa-02a3-485f-bf35-63f800ede160
https://youtu.be/Me4DnSytjqU

Hours Spent: 1.5Hrs

## 18/12/25 - 1st Iteration of LM3915 cascading circuit on Circuit Wizard

I then looked to create a cascading circuit with the LM3915. This is when you combine two chips and two LED bar graphs so that one LED bar graph turns on fully and then the other begins to turn on once the first one is entirely on so it creates a single bar. This was my first attempt on circuit wizard to create a cascading circuit with the LM3915. However, the attempt was unsuccessful. 

<img width="363" height="321" alt="image" src="https://github.com/user-attachments/assets/fc15e040-1131-4ddd-b515-c4d030c1a04f" />
<img width="365" height="213" alt="image" src="https://github.com/user-attachments/assets/04292d4a-1dc0-4c92-be88-5447f8b5f867" />

https://github.com/user-attachments/assets/24a29da8-6dcd-465d-8769-79b624df0bc3
https://youtu.be/CXn7GhCSTSc

On my second attempt, one LED bar graph remained on for the full time while the other bar graph turned on sequentially.   

<img width="506" height="508" alt="image" src="https://github.com/user-attachments/assets/ada5a91c-f880-4ec9-ba55-8f20fbfa90a8" />

https://github.com/user-attachments/assets/679a3a3f-da81-4daf-b225-d38ebaf53af2
https://youtu.be/CXn7GhCSTSc

For my third attempt, I followed the LM3915 datasheet for the circuit diagram that is shown on the left. This still did not work as expected. The LEDs on both of the bar graphs remained on fully. 

<img width="621" height="190" alt="image" src="https://github.com/user-attachments/assets/83e2ad63-e6c5-44ee-9280-c3730a360ffb" />
<img width="468" height="292" alt="image" src="https://github.com/user-attachments/assets/ba3f25e4-1ea3-4f40-ad03-81a52efe4362" />

https://github.com/user-attachments/assets/b65bbbcb-cd1e-4f91-b2d6-47c6a777f7b1
https://youtu.be/uaubeiE09Kw

On my fourth try, I used another method of cascading the LM3915 from the datasheet. This worked better than before but still was not perfected as there was an overlap of LEDs between the bar graphs.

<img width="465" height="290" alt="image" src="https://github.com/user-attachments/assets/7a990614-e487-4bde-953b-d485cd14c018" />
<img width="561" height="239" alt="image" src="https://github.com/user-attachments/assets/585ea9c7-710a-473a-b900-d68258ee64fc" />

https://github.com/user-attachments/assets/2ea70734-821a-4d35-a42e-a8c377013a76
https://youtu.be/CSH4s-Md3LM


After many failed attempts, I changed my schematic to a another one as shown on the right. After connecting this up, it worked perfectly as all the LEDs turned on for the first bar graph before they turned on for the second bar.  I also fixed the order in which they turned on.

<img width="434" height="295" alt="image" src="https://github.com/user-attachments/assets/0dfb5dcf-75ae-4591-b96b-169139d9e0d6" />
<img width="515" height="221" alt="image" src="https://github.com/user-attachments/assets/eceded9c-47aa-46ed-87f0-f092bbac3b84" />

https://github.com/user-attachments/assets/6c0bd98b-783c-4b2b-b63f-a9d15f8ed98b
https://youtu.be/nnO8k_CH0iI


Hours Spent: 2.5Hrs

## 20/12/25 - 1st Iteration of LM3915 cascading circuit 

Using my working circuit wizard schematic, I breadboarded the cascading circuit and used a 1K potentiometer to act as the input signal which will be replaced by the microphone circuit amplified by the LM386 amplifier that I had breadboarded earlier. Upon changing the resistance of the potentiometer, the LEDs worked as expected and they turned on sequentially. This created the 20 LED scale that I will use in my project.
https://youtu.be/IikYA9wNV6s
https://github.com/user-attachments/assets/0518f570-b7a8-470e-89ca-3e4b90909c6f

Hours Spent: 1Hrs

## 21/12/25 - 1st Iteration LM386

To create the amplifying circuit for the microphone, I had two component options : the LM386 and the TDA7266. I chose to begin with the LM386 Op-amp which was the simpler but in turn weaker amplifier. This was my first attempt at creating the amplifier circuit with the LM386 to amplify the microphone signal and input it into as the analogue signal for the LM3915 instead of the current potentiometer. However my attempt was not entirely successful as the circuit was too sensitive and some LEDs remained on even when there was no audible sound. One of the reasons that this could be happening is because of the constant but quiet 50Hz of Alternating current. The fix for this is too include some way of altering the sensitivity of the microphone signal that is being amplified. After some research, I found that a method of doing this would be to include a potentiometer between the input signal pin in the amplifier chip and the microphone.

<img width="320" height="270" alt="image" src="https://github.com/user-attachments/assets/3242dd92-e2e7-44d5-b943-4d135e362acf" />
<img width="410" height="236" alt="image" src="https://github.com/user-attachments/assets/0b2e51fb-70b4-4be8-9426-c3a4010e673b" />

Hours Spent: 2Hrs

## 22/12/25 - 2nd Iteration of LM386

For the second attempt, I used a 10K potentiometer between pin 3, the analogue input signal for the amplifying chip, and the microphone, as seen in the circuit diagram below, allowing me to adjust the sensitivity of the microphone. This worked effectively and meant the LEDs remained off when there was no audible sound that could be heard by the human ear. 

<img width="412" height="356" alt="image" src="https://github.com/user-attachments/assets/1eeb9ad2-73d4-45e2-84d8-760b4151d370" />
<img width="590" height="231" alt="image" src="https://github.com/user-attachments/assets/e509985b-2aa8-4cdc-b169-d272342992e7" />

Hours Spent: 1Hrs

## 24/11/25 - 1st Iteration of LM3915 and LM386

I connected my LM386 amplifier circuit to the analogue input signal of the LM3915 which is pin 5. On doing this, the LEDs turned on as the microphone picked up sound. However, the LEDs turned on simultaneously as the microphone detected sound. They should have turned on one by one as volume increases and then turn off one by one as it decreases. I played around with the sensiivity yet found it made very little difference. I wondered if the circuit was breadboarded correctly and I checked each connection with the the various datasheets and found no errors. 

https://github.com/user-attachments/assets/eb3f0788-d1ea-40c4-9e93-2418777b1dde
https://youtu.be/DyySWVqZpqs

I concluded that the LM386 amplifier was not strong enough to amplify the signal to a high enough range to power the LEDs. Therefore, I switched to a much stronger amplifier: the TDA7266. The TDA7266 is meant to amplify the signal from the microphone to a signal high enough for speakers. Thus, it should be more than sufficient for powering the range of the LEDs. 

<img width="287" height="290" alt="image" src="https://github.com/user-attachments/assets/24317ad5-b548-41f2-be8a-bf2fa25c2812" />

Hours Spent: 2hrs

## 26/12/25 - Researching TDA7266

To create the TDA7266, I looked into the datasheet to see what I needed to connect and how it worked before prototyping. After reading through a lot of it, I made notes on the important parts of the circuit and the functionality of them and simplified the schematic significantly while still making sure the amplifier would work. 

Pin 1(OUT1+): Output pin for the red (positive) wire of the speaker. This is the one we will join to the input pin of the LM3915
Pin 2(OUT1-): Output pin for the black (negative) wire of the speaker. This is not required for the LM3915.
Pin 3 and 13(VCC): Power supply (plus volts) connected with two capacitors
Pin 4(IN1): Input signal from microphone with 0.22 microfarads capacitor(or a value close enough)
Pin 7(ST-BY): This controls whether the amplifier is active or in Standby by using a voltage threshold
Pin 9(S-GND): Power supply (0V/ ground)
Circuit wizard didn't have this component available either so instead I breadboarded it directly and have attached an image of my working breadboard as well as the circuit diagram provided in the datasheet.

To combine the microphone with the TDA7266, the microphone requires its own circuit. This consists of a 1.5K resistor connected from the ground voltage to the ground pin of the microphone (shown by the metal connecting the pin to the outer casing of the microphone). The positive pin connects to pin 4 of the TDA7266.

Hours Spent: 1.5Hrs

## 27/12/25 - 1st Iteration of TDA7266

I breadboarded the TDA7266 circuit and I used the speaker to test whether the microphone and my amplifier circuit were working. Once I powered my circuit, I should have heard a click from the speaker when the microphone picked up on some sound but this did not occur. Upon further inspection, it was clear that the pins of the amplifier chip were not in the breadboard. This was due to the awkward shape of the pins. To fix this I used a pair of pliers to bend and force the pins into the breadboard. Once the pins were fitted in, I again powered the circuit and used the speaker to test the circuit. This time I could clearly hear the speaker when the microphone picked up sound.

<img width="443" height="358" alt="image" src="https://github.com/user-attachments/assets/95cf609a-b55c-468e-abf9-08a61deb40c5" />
<img width="251" height="499" alt="image" src="https://github.com/user-attachments/assets/d5f657b4-1f86-4e0c-a022-97417393c75f" />
<img width="263" height="495" alt="image" src="https://github.com/user-attachments/assets/da23a178-ba4e-47eb-8679-33a1c240f8ed" />

Hours Spent: 2Hrs

## 28/12/25 - 1st Iteration of LM3915 and TDA7266

With a working microphone amplifying circuit using the TDA7266, I then looked at combining it with the LM3915. I connected the output pin from the TDA7266 to the signal input pin in my LM3915 cascading circuit. After powering on the entire circuit, I tested the combination. When the microphone picked up sound, the speaker still outputted this sound, ensuring that the TDA7266 was working as expected. However, despite connecting the circuits together, the LM3915 remained on fully, regardless of the microphone signal. Upon inspection of my breadboard, I noticed that one of the capcitors' legs were "loose". i could barely see it so it took me a while to notice but somehow the capacitors leg had snapped probably from when I packed away my breadboard. Howeever, evan after replacing the capacitor, I had the same issue. But this time the speaker was clicking so that was good :)

https://github.com/user-attachments/assets/f45f54c8-7b37-46e5-acf5-42d902fe9c2a
https://youtu.be/URjmhI465j8

Both circuits worked as expected individually, but when combining the two, they failed to produce the desired outcome. My first thought was that the TDA7266 used two output pins as one was meant for the black speaker wire( zero volts) and the other for the red speaker wire (plus volts) but I only used one wire going from the plus volts output pin to the signal pin. However, this should not affect the circuit as it is only for grounding the speaker. I did a lot of searching online to find the issue as I could see no problems whth my circuitry and in theory it should have worked. The issue was something that neither datasheet mentioned and I found the solution on a forum. I added a 100k resistor connecting the signal pin to ground but still allowing current to flow. This provided a reference for the LM3915 to sense voltage changes(from the microphone) from ground. Before, the signal from the amplifier was "floating" as it had no reference of what a high signal was and a low signal was and the resistor provided that reference. At least that's what I make of it :)

https://github.com/user-attachments/assets/a47a75ed-9d45-499d-acfb-030a4748a6d8
https://youtu.be/v66TnnIR2ss

Hours Spent: 2.5hrs

## 29/21/25 - Designing the PCB

Now that I had a working breadboard, I looked at making a Printed Circuit Board to house the components for my project. I thought about making 3 PCBs for the 3 different parts of my project. One for the TDA7266 amplifying circuit with the microphone. One for the LM3915 IC. And one for the LED bar graphs. I started with the LM3915 PCB. Below is my first attempt. When I tested the PCB, I found that the top LED bar graph turned on before the bottom one did which is the opposite of what was expected.

https://github.com/user-attachments/assets/6355bcd3-a77e-4e1f-9847-a17f8e9ea8c8
https://youtu.be/dl0ivdptw8o

To fix the mistake, I switched the circuitry for the chips around. This time when I powered my circuit, it worked perfectly and as expected. All of the LEDs on the bottom bar graph turned on sequentially and then all of the second LED bar graph turned on in the same way.

https://github.com/user-attachments/assets/0eb5199e-d0a9-4525-8dbc-cb6500f1c272
https://youtu.be/Y7GG71hULfE

I now had to create the PCB to have the LM3915 cascading circuit 3 times. I connected two PCB tracks from each end of the circuit. The one at the top going to all the circuits connected the plus volts. The one on the bottom connected to ground. This meant I only needed 2 wires from the battery pack to the tracks at either end, instead of using 6 wires going to each chip individually.

https://youtu.be/F8g8QQieGRA
https://github.com/user-attachments/assets/5b7bbdbe-f083-471c-ab66-015706b1e16d

Hours Spent: 2Hrs

## 30/12/25 - Fixing my final PCB

I realised that my final PCB was using the wrong potentiometers to what I had readily available and that Circuit Wizard doesn't actually have a schematic for the pot that I was going to use. So, I just used three copper pads instead and placed them to the size of the pot that I will be using. This did mean I had to measure the potentiometers' leg spacings individually and match it with the spacing ofthe rid on Circuit Wizard. I also had to redesign a lot of the PCB as the old pot had large spaces allowing the tracks to passthrough but this one did not.

<img width="536" height="350" alt="image" src="https://github.com/user-attachments/assets/07ef4755-a293-4e13-b239-8734cf34d17f" />

Hours Spent: 1Hrs

## 31/12/25 - Producing the PCB

First, I printed my circuit onto an acetate sheet. This will be used to make my circuit tracks on the pcb. 

<img width="248" height="225" alt="image" src="https://github.com/user-attachments/assets/fba63467-295a-4f0d-a801-f597d904dc86" />

Then I used the guillotine to cut the copper plated board into the correct size for the PCB.

<img width="313" height="200" alt="image" src="https://github.com/user-attachments/assets/d087cf19-3176-4c4b-80f3-5459cde76cd5" />

I then placed the acetate sheet on the copper side of the PCB and used the UV exposure box to soften the photoresist layer on the copper board.

<img width="305" height="138" alt="image" src="https://github.com/user-attachments/assets/c1c4f265-8922-47c3-bb03-ba6d132fb32f" />

Then using developer solution, I developed the tracks and used an acid etch tank to remove the excess copper.

I then had a PCB ready. I used a multimeter and used continuity mode to ensure the tracks were all connected.

While drilling holes in my PCB, I realised that I forgot the copper pads where I would solder wires and connect my other PCB with the LEDs, shown by the red circles below. 

<img width="542" height="339" alt="image" src="https://github.com/user-attachments/assets/1fe9dbd1-5f26-4630-b0ba-b35d97625465" />

Hours Spent: 3hrs

## 2/01/26

I added in the pads and remade my PCB. Again, using the multimeters' continuity mode, I tested whether the tracks were all connected. I then began drilling the holes on the PCB which took some time considering there were over 200 holes which I had to hand drill! I then began soldering some of my components.

<img width="387" height="231" alt="image" src="https://github.com/user-attachments/assets/0b0bdfa5-8d3c-4acf-9994-e0d7dfc819d1" />
<img width="362" height="237" alt="image" src="https://github.com/user-attachments/assets/5d68946d-fd5c-496b-9932-0d1b6d78b969" />

Hours Spent: 2.5hrs

## 3/01/26

I finished soldering the components and all of the wires which was a LOT! I now have a love hate relationship with wires. I ran out of 18 pin DIL sockets so I just shaved down some 20 pin ones instead and it seems to do the trick.

<img width="494" height="439" alt="image" src="https://github.com/user-attachments/assets/e54c1c0f-41ff-4b7d-9512-563f0a9a5809" />

Hours Spent: 2Hrs

## 4/01/26 - Designing the LED PCB

I began designing the PCB for the LED bar graphs to sit on the top of all of the PCBs. I made sure that it was small enough to fit in my hand but big enough to cover the entire of the main PCB which was quite big.

<img width="422" height="284" alt="image" src="https://github.com/user-attachments/assets/1e4e671f-a5cd-4b52-b187-446c90282586" />
<img width="423" height="264" alt="image" src="https://github.com/user-attachments/assets/fd7f832e-75ef-4d39-90d4-6c89e44ed478" />


Hours Spent: 1Hrs

## 6/01/26 - Producing the LED PCB

I produced the PCB and once again tested the continutity of the tracks using a multimeter. Everything looked good so I began drilling the 360 holes with a hand drill :( Atfer finally finshing drilling and fighting hand cramp, I soldered the LED bar graphs which was easy enough.

<img width="643" height="391" alt="image" src="https://github.com/user-attachments/assets/a5c21175-f3d7-43a0-8f4c-437e247f3dbd" />

Hours Spent: 1.5Hrs

## 7/01/26 - Testing the PCBs

I combined the LED bar graph and the control PCB. 

It didn't work :( 

I tested the LED PCB which was working perfectly so it has to be the control PCB. I used a logic probe to test each pin and each track of my control PCB and noticed a lot of mistakes. I required a lot of wire jumpers and also forgot to have a track connecting ground for all f the different parts of the circuit. I had to redesign and remake it. At least I don't have to drill 360 holes this time, only 200 :(

<img width="352" height="552" alt="image" src="https://github.com/user-attachments/assets/56df9ef9-7152-4ab7-ab07-a66ee0d5dcc0" />

Hours Spent: 2hrs

## 8/01/26 - Redesigning the main PCB

I decided to completely redesign my PCB and start from scratch. This was extremely difficult and time consuming to make sure all the tracks were connected and did not cross but also keep it at a acceptable size. But in the end, after a lot of attempts, I managed to simplify it and remove all of my wire jumpers and also reduce the size significantly. ( It now fits within the palm of my hand!!!)

<img width="262" height="386" alt="image" src="https://github.com/user-attachments/assets/ab6d3571-4391-4777-83c7-882de8933bfa" />
<img width="467" height="340" alt="image" src="https://github.com/user-attachments/assets/be4df7e0-2f32-49fe-81b7-e6d171a67bb6" />
<img width="487" height="341" alt="image" src="https://github.com/user-attachments/assets/545e6d23-0b49-40a6-bd3b-06c12e9b88d1" />
<img width="211" height="340" alt="image" src="https://github.com/user-attachments/assets/ed1310c6-e0ae-4416-9b8c-9f1a1eefb53a" />
<img width="428" height="307" alt="image" src="https://github.com/user-attachments/assets/508504e3-0825-4bcf-9e40-472b345b2cb4" />
<img width="658" height="503" alt="image" src="https://github.com/user-attachments/assets/001398ef-a524-4d61-9829-1116ccaf96a1" />

Hours Spent: 2Hrs

## 9/01/26 - Producing the redesigned main PCB

Once more, I produced my PCB and tested the continuity using a multimeter. Once ensuring all tracks were connected, I promptly began the drilling of ALL the holes. Yes All 200 :(

<img width="400" height="211" alt="image" src="https://github.com/user-attachments/assets/1de8ff2a-ece3-4670-9228-99cc21aa90d7" />

Hours Spent: 1.5Hrs

## 10/01/26 - Soldering my PCB

I began and managed to complete all of the soldering of my PCB. I decided not to solder every wire this time, only a couple for testing first. 

I connected both PCBs. I connected the power wires to my breadboard. And then I switched on my power supply......

And IT WORKED!!!!

Hours Spent: 1.5hrs

## 12/12/25 - TDA7266 PCB

I began designing my final PCB: the TDA7266 amplifier with the microphone. This was difficult as my working protoype was slighlty different to the schematic on the datasheet, but I managed in the end using a multimeter to test the values of all my components in my PCB. 

<img width="524" height="383" alt="image" src="https://github.com/user-attachments/assets/cc06ef15-ed41-4fdf-ace4-4acc732d147e" />
<img width="519" height="372" alt="image" src="https://github.com/user-attachments/assets/fd6d4ddf-ae5c-4138-8f81-976d7717107b" />


Hours Spent: 1Hrs

## 03/02/26 - Catching up

Had to take a slight break because of exams but they're finally finished now!!! :)

I examined my PCBs and noticed that the main PCB that controls everything seemed damaged. The copper tracks seemed to have peeled off possibly due to the intense repeated heat of the soldering iron when soldering ALL of those pesky wires. After a quick test, I realised that it was broken.

I give up.

JK.

I am going to simplify it first though. Instead of having 6 columns ill only do 1. However instead of only 2 LED bargraphs per column I'm making it 3 so it has a range of up to 90dB.

Also After some research I found that instead of using wires, I could use pin sockets and headers. These will be much easier to solder and also will be much better visually and for testing as the PCBs will be able to split apart.

<img width="259" height="194" alt="image" src="https://github.com/user-attachments/assets/4b9a97d3-5250-4b7c-8708-67c6c2c82795" />
<img width="1220" height="608" alt="image" src="https://github.com/user-attachments/assets/5be9d82a-019d-45ff-9e47-10de22c1f593" />

Hours Spent: 1Hrs

## 04/02/26 - Designing my new Schematic

I drew the schematic for my new design in Circuit Wizard. After doing so many schematics of the LM3915, I have practically memorised all the pin connections. I looked through the datasheet and online schematics to see if I needed something different for the third LED bar graph. I concluded that it should work in the same way as the 2nd one so I produced it in the same way. I connected the Ref high of the middle IC to the ref low of the top IC. After a quick test on circuit wizard it seemed to work perfectly.

<img width="1028" height="626" alt="image" src="https://github.com/user-attachments/assets/5787a934-2792-4660-befd-bb3fb2a90947" />

Hours Spent: 1Hrs

## 06/02/26 - Designing my new PCB

I designed my PCB using the working schematic I created. I began with the main control PCB with the LM3915s. It was extremely difficult to ensure all tracks were connected together without using any zero ohm resistors or wire jumpers. I managed this however it resulted in many tracks being very thin which can be an issue while producing the PCB. I added the pin sockets to the output pins of the LM3915. Although, the first output pin is on the opposite side of the IC to the rest and there was no way to draw a track to connect the pin to the pin socket. Therefore, instead, I used a 9 pin socket and used a copper pad for the first output pin where I will solder a wire that connects to the other PCB. I then created the PCB for the LED bar graph. This was quite simple as one side was all connected to plus volts. The other side was connected to the pin headers. I made sure that the two PCBs would line up so that they would stack easily.

<img width="542" height="773" alt="image" src="https://github.com/user-attachments/assets/cfa884a0-1017-41e4-bfc5-7abf919c7020" />

Hours Spent: 1.5Hrs

## 08/02/26 - Designing my new PCB in KiCad

I was scared about the tracks being too thin and the acid etch tank not being able to produce the tracks and thus the PCB properly so I thought about using JLCPCB instead.

However, Circuit Wizard doesn't let me export my PCB as a gerber so I have to redesign it in KiCad.

This was a LOT quicker than Circuit Wizard because of the auto routing tool and also allowing for tracks on both the front and the back of the PCB

I uploaded it to JLCPCB and saw that my PCBs would be under 10gbp in total but I would have to wait 12 days for it to be delivered. I decided that I would try the acid etch tank PCB first and use this if that fails.

<img width="536" height="915" alt="image" src="https://github.com/user-attachments/assets/39552dbf-65c1-4aa4-96e2-d785b681625d" />

<img width="626" height="781" alt="image" src="https://github.com/user-attachments/assets/9b0553b9-1664-4c03-95f2-0deda48164b0" />

<img width="1043" height="984" alt="image" src="https://github.com/user-attachments/assets/9f11eee4-d3d3-4265-9d4e-c839acbea972" />

https://lapse.hackclub.com/timelapse/Xt3aB62gZel_

Hours Spent: 1Hrs

## 09/02/26 - Producing my new PCBs 

Same as I had done many times before, I produced my PCBs. I made the LED PCB, the control/LM3915 PCB and the TDA7266 PCB with a small PCB for a mic and a switch. In total I made 5 PCBs today. As always, I used a multimeter to test for continuity of tracks and once I confirmed everything was working, I began drilling the holes in the PCB for the components. I noticed that I had missed 2 pads for the power wires going to the TDA7266 so I drilled holes close to the tracks without actually touching the tracks. Then I soldered a wire through the holes and used solder to connect it to the tracks. 

Hours Spent: 2Hrs

## 09/02/26 - Soldering my new PCB

I completed the soldering of all of the components of my new PCBs. I then began testing my main LM3915 PCB. I tried to use my old breadboard where I produced the prototype circuits however I noticed that my once working circuit weren't working anymore and that the power supply was showing that there was a short circuit. I think the breadboard itself is damaged so I used another breadboard instead. It was difficult to connect the wires of my PCB to the breadboard because I was using multistrand wire instead of single strand wire so they just kept popping out. Eventually I managed to keep them in long enough to test it and prove it works and take a picture. Thankfully, when I connected the signal pin to plus volts all the LEDs I had connected were on showing that the PCB works. Also the ICs weren't overheating and the power supply only had a green light so luckily there were no short circuits.

<img width="543" height="658" alt="image" src="https://github.com/user-attachments/assets/6c47be39-c04a-450b-bfb7-c73b9616a4bb" />

Hours Spent: 1.5Hrs

