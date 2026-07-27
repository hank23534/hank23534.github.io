Currently I have made the first prototype for the frequency counter and am currently working on the second version. The version displayed here can accurately count from 2 hz
to 1 Mhz with nine digit accuracy. While this is good enough for most hobby applications it's still a ways away from the 100 mhz to 100 Mhz design goal. After some testing I 
can easily get the counter to go to 10 Mhz with some modification. The main problem for HF is that the PCB board doesn't have a proper ground plain and proper
termination. This will be the next major change to the design as currently the whole counter is on a single FR4 PCB. For the next design there will be an HF board that contains
the Input amplifiers and counter circuitry that run at HF, the rest of the circuit, MCU, PSU, and other Lower frequency/DC components will on a separate regular PCB. 
This new design should easily be able to obtain 10 Mhz, however I'm not sure how much higher than that can be obtained. I'll be using BFR92P NPN BJTs for the input stage 
they are designed for broadband amplifiers up to 2 Ghz so they should work fine for this project. The other main upgrade will come to the Counter circuitry. The SN74LV8154N and
most of the logic ICs cap out at about 40 Mhz, So they will need to be replaced as well. For the new counters and logic gates I'm going to select all SMD components to help
lower cost and size of the project. For the nine character VFD I'm using for a display I've simplified the driver to use just a shift register and multiplexer. The main issue
with the VFD driver is the scanning method makes it difficult to take photos of the display without dimming the lights and cranking the exposure on the camera
(looks good in person though). I'll attach some photos below of the counter and some results.


3.1 HZ
![3.1HZ IMG Error](https://github.com/hank23534/Home-Brew-Frequency-Counter-/blob/main/Photos/3.1HZ.jpg)

100 KHZ
![100KHZ IMG Error](https://github.com/hank23534/Home-Brew-Frequency-Counter-/blob/main/Photos/100%20KHZ%20.jpg)

1 MHZ
![1MHZ IMG Error](https://github.com/hank23534/Home-Brew-Frequency-Counter-/blob/main/Photos/1%20MHZ.jpg)
