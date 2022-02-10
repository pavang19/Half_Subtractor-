# Design and Implementation of Half Subtractor using Sky 130nm Technology
This repository presents the Design and implementation of Half Subtractor uing eSim (An open-source Electronic Design Automation tool  and Sky 130nm PDKs (Process Design Kit).
## Table of contents
#### 1.[ABSTRACT](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#1-abstract )
#### 2.[eSIM EDA TOOL](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#2esim-eda-tool)
#### 3.[Sky130 PDK](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#3sky-130-pdk)
#### 4.[CIRCUIT DESIGN](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#4circuit-design-1)
#### 5.[IMPLEMENTATION](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#5implementation-1)
#### 6.[RESULTS](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#6results-1)
#### 7.[REFERENCES](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#7references-1)
#### 8.[ACKNOWLEDGEMENT](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#8acknowledgement-1)
#### 7.[AUTHOR](https://github.com/pavang19/Half_Subtractor-/edit/main/README.md#7author-1)

### 1. ABSTRACT
This project proposes  the design of a half  subtractor.Subtractor Is a digital circuit that performs subtraction of two numbers.  It has two inputs and two outputs. This circuit is employed to subtract two single bit binary numbers A and B.In many computers and other kinds of device processors, subtractors are used in ALU operations and  are also frequently used in other parts of the processor.Depending upon the application of the device or upon the purpose of the application to be performed, the inputs to the circuit device may vary from two to 3. We could possibly use a Half-Subtractor if there are two inputs while for 3 inputs, a Full-Subtractor may be used.In this project the circuit schematic is designed using Sky 130nm PDK(Process Design Kit)  on eSim, an open source EDA tool and simulated on an open source spice simulater Ngspice.


### 2.eSIM EDA TOOL
eSim is a free/libre and open source EDA tool for circuit design, simulation, analysis and PCB design. It is an integrated tool built using free/libre and open source software such as KiCad, Ngspice and GHDL.eSim offers similar capabilities and ease of use as any equivalent proprietary software for schematic creation, simulation and PCB design, without having to pay a huge amount of money to procure licenses. <br /> 
Main features of eSim- <br />
-Draw circuits using KiCad, create a netlist and simulate using Ngspice. <br />
-Design PCB layouts and generate Gerber files using KiCad. <br />
-Add/Edit device models(Spice Models) and subcircuits using the Model Builder and Subcircuit Builder tools. <br />
-Perform Mixed-Signal Simulation. <br />
-Support for Ubuntu OS and Windows OS <br />
-It allows the creation and modification of components and symbol libraries.<br />
-Apart from Ngspice plot eSim provides an interactive plotting frontend where user can select nodes or branch and plot voltage or current respectively.<br />
For more information: https://esim.fossee.in/home


### 3.Sky 130 PDK
Google and SkyWater Technology collaborated to release the industry’s first open source foundry process design kit (PDK) known as SKY130 (130 nm CMOS technology) under an Apache 2.0 license, giving designers worldwide access to use the technology for new IP functions as well as complete open source ASICs.<br />
For SkyWater Open Source PDK documentation :https://skywater-pdk.readthedocs.io/en/main/  <br />
To download Sky130 PDK :https://static.fossee.in/esim/installation-files/sky130_fd_pr.zip


### 4.CIRCUIT DESIGN
The 1-bit  half subtractor accepts two binary inputs A and B and produces the output difference and borrow.The proposed design can have four possible combinations of inputs and corresponding four outputs of difference and borrow respectively.The input combinations are 00,01.10 and 11 .<br />
The truth table of 1-bit Half Subtractor is as below-<br />

![image](https://user-images.githubusercontent.com/55171083/153249289-4f9fac23-7584-4c8c-a92e-be8a984fc4b1.png) <br />

The borrow output is only high when A is 0 and B is logic 1.
Borrow = A'B <br />
The output of the difference is same as the output of the Xor gate. <br />
Difference = A XOR B  <br />


**REFERENCE CIRCUIT DIAGRAM**

![Reference_circuit_diagram](https://user-images.githubusercontent.com/55171083/153257879-8c34378a-a568-4196-8c4d-6f7c946926cc.png)



### 5.IMPLEMENTATION
The schematic of half subtractor is designed on eSim .CMOS logic consists of one pullup and pulldown network .The pullup network consists of pmos whereas the pull down network consists of nmos. The circuit has mainly an inverter for obtaining the inverted input and an AND gate which is used to design the borrow and an XOR gate is used to generate the difference output.<br />
The AND gate is implemented using CMOS design with 2 pmos in series and two nmos in parallel.Similarly the XOR gate is also realized using CMOS design with four pmos and four n-mos transistors in the pullup and pull down network respectively.

![Schematic_half_subtractor_esim](https://user-images.githubusercontent.com/55171083/153259801-2809f3b3-06e3-49c6-bdd9-ca3f8136bda7.png)

After doing the Schematic spice netlist is generated. <br />The auto generated netlist can be found below.<br />
[auto_generated _spice_netlist.txt](https://github.com/pavang19/Half_Subtractor-/files/8035517/auto_generated._spice_netlist.txt)

Next the spice Netlist is Modified with respect to Sky 130 nm models .<br />The Modified spice netlist is below:<br />
[Modified_spice_netlist.txt](https://github.com/pavang19/Half_Subtractor-/files/8035522/Modified_spice_netlist.txt)


And the .cir file is saved inside the sky 130 pdk folder and it is simulated using ngspice.



#### 6.RESULTS
The circuit is simulated using Ngspice simulator .
SPICE SIMULATION RESULTS:

![spice_simulation](https://user-images.githubusercontent.com/55171083/153264099-3a9f55f2-8066-4b42-beaa-ad1e22355c17.png)

NGSPICE WAVEFORM

![ngspice_waveform](https://user-images.githubusercontent.com/55171083/153271696-a5faa385-49ce-4179-b697-055ba7a7d450.png)


The above waveform matches with the reference waveform and the truth table ,hence the design is implemented successfully and verified.


### 7.REFERENCES
[1] Tanvi Sood,Rajesh Mehra(2013) Design of a low power half subtractor using 90um cmos technology .IOSR Journal of VLSI and Signal Processing.https://www.iosrjournals.org/iosr-jvlsi/papers/vol2-issue3/H0235156  <br />
[2] Monikashree T.S, Divya A, Kithara V, Nithya Shree S,Area efficient Full Subtractor design using CMOS Technology.ITSI Transactions on Electrical and Electronics Engineering (ITSI-TEEE) <br />


### 8.ACKNOWLEDGEMENT
* [Kunal Ghosh](https://github.com/kunalg123), Co-founder of VLSI System Design (VSD) Corp. Pvt. Ltd 
* [SAFAL COE ,KARNATAKA](https://www.sfalcoe.com/)


### 9.AUTHOR
PAVAN P GUTTI , 5th sem B.E (ECE), SDM COLLEGE OF ENGINEERING AND TECHNOLOGY  ,DHARWAD-580002
* Contact : pavan.gutti2@gmail.com



