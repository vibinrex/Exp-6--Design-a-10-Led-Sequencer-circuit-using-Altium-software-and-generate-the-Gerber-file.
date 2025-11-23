# Exp-6--Design-a-10-Led-Sequencer-circuit-using-Altium-software-and-generate-the-Gerber-file.
# AIM:
To design the schematic and PCB layout diagram of an LED Sequencer circui circuit using Altium software.
# EQUIPMENT REQUIRED:
●	Hardware: Personal Computer (PC)<br>
●	Software: Altium  <br>
# PROCEDURE:
Open Your PCB Project<br>
	Launch Altium Designer.<br>
	Open your completed PCB design project (.PrjPcb).<br>
	Ensure your PCB layout is finalized, with correct layers, footprints, and clearances.<br>
Check Design Rules and Electrical Rules<br>
	Go to Tools > Design Rule Check (DRC).<br>
	Run checks for clearance, short circuits, and net connectivity.<br>
	Fix any errors before generating outputs.<br>
Open the Output Job File (Optional)<br>
	Go to File > New > Output Job File to create an .OutJob file.<br>
	Add Gerber Files, NC Drill Files, and other manufacturing outputs as needed.<br>
Generate Gerber Files<br>
	Go to File > Fabrication Outputs > Gerber Files.<br>
	In the Gerber Setup window, configure:<br>
o	Units (mm or inch)<br>
o	Format (usually 4:4 or 2:5)<br>
o	Layers to Plot: Select top layer, bottom layer, solder mask layers, silkscreen layers, etc.<br>
o	Set Aperture and Plot Options (mirror, include pad holes, etc.)<br>
Generate NC Drill Files<br>
	Go to File > Fabrication Outputs > NC Drill Files.<br>
	Configure settings like units, format, and which holes to include.<br>
	Click OK to generate the drill files.<br>
Preview Gerber Files<br>
	Use CAMtastic or any Gerber viewer (Altium has one built-in) to preview the files.<br>
	Go to File > Import > Gerber, and inspect the output visually.<br>
 Export Files<br>
	All generated files will be saved in the Project Outputs folder.<br>
	Zip all relevant files (Gerbers, NC Drill, ReadMe, Fab notes) and send to the manufacturer.<br>

# THEORY:

555 Timer as Clock Pulse Generator<br>
In the circuit, the 555 timer IC is configured in astable mode, which means it generates continuous square wave pulses without any external triggering. The resistors (R1 and R2) and the capacitor (C1) connected to the timer determine the timing frequency. These pulses appear at pin 3 of the 555 timer and serve as clock inputs for the next stage — the CD4017 counter. The frequency of blinking (how fast LEDs move from one to another) depends on the values of R1, R2, and C1.

CD4017 Decade Counter for Sequential Switching<br>
The output pulses from the 555 timer are connected to pin 14 (Clock) of the CD4017 decade counter. This IC has 10 output pins (Q0–Q9), each going HIGH one at a time in sequence for every clock pulse it receives. The RESET (pin 15) is grounded to allow full counting, and ENABLE (pin 13) is also grounded to ensure the counter functions without being disabled.

LEDs Connected to CD4017 Outputs<br>
Each of the 10 outputs (Q0 to Q9) is connected to an individual LED via a current-limiting resistor (R3 to R12). When an output pin goes HIGH, the corresponding LED turns ON. On the next clock pulse, the output shifts to the next pin, and the LED connected to that pin lights up. This creates a chasing LED effect, where only one LED is ON at a time, and it moves in a sequence from D1 to D10.

Cyclic Repetition of Sequence<br>
After reaching Q9 (D10), the CD4017 automatically resets back to Q0 (D1) on the next clock pulse, creating a continuous loop of sequential lighting. This cycle will keep repeating as long as the 555 timer continues to produce clock pulses.

Power Supply and Grounding<br>
The circuit is powered by a DC supply (typically 5V or 9V) connected at the VCC and GND lines. All ICs and components share a common ground to maintain correct operation.

# CIRCUIT DIAGRAM:
![image](https://github.com/user-attachments/assets/2cb084f1-22ea-4d4e-816d-eee72cd2918f)

 
# EXPECTED OUTPUT:
## Schematic diagram:

![Screenshot 2025-11-23 212244](https://github.com/user-attachments/assets/b5e743c7-e90e-4e54-ae93-7256fff97610)

 
## Layout diagram:

![Screenshot 2025-11-23 212344](https://github.com/user-attachments/assets/36e468cb-d6d0-4459-aedc-f85a46a6e5b0)

 
# RESULT:
Thus, the schematic and PCB layout for the LED sequencer circuit has been successfully designed using Altium software.

