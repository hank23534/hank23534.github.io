  In my previous write up I documented how the basic counting methodology and core counting IC for this project work. In this post I will explain the counter latch circuitry 
  that helps to simplify the interaction between the MCU and counter circuitry. The latch consist of four IC a 74VHC393FT (4 bit synchronous counter), SN74HC14AN Schmitt
  inverter, 74HC08D AND gate, and a CD74HC74E D-FlipFlop. The process starts with the MCU clearing the main pulse counter and the 74VHC393FT. After the 74VHC393FT is cleared
  the D flip flop data bit is set to 1 and upon the next rising edge of the input signal Q will be set to 1. After Q is set to 1 the first AND gate is enabled allowing the
  74VHC393FT to begin counting. When 2QA goes high it enables the second AND gate and the main pulse counter begins counting clock pulses. When 2QB goes high its output is 
  fed through an inverter then into the data input of the D-FlipFlop. when 2QB goes high 2QA goes low stopping the pulse counter from counting anymore pulses. On the next 
  input clock pulse the FlipFLop reads the 0 and loads it into Q thus stopping the 74VHC393FT from counting any more. That counter latch will remain in this state until
  the 74VHC393FT is reset. While the latch is disabled the MCU can take its time to read data from the pulse counter before resetting the latch to get another sample. The 
  MCU is made aware of the latch completing a cycle via the Gate signal (AKA the inverted output of 2QB) on the falling edge of the Gate signal the MCU knows the counter is ready
  to be read.


  I have upload a schematic of the full Counter and a Logisim file [Here](https://github.com/hank23534/Home-Brew-Frequency-Counter-/tree/main) used to gain an intuitive understanding of the circuity. !(NOTE: the second FlipFlop in the schematic
  was scrapped in the final design it just wasn’t removed from the schematic yet).
  
