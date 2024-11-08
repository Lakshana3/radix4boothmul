# Radix-4 8-Bit Booth Multiplier with Preencoded Mechanism

This project includes the design and simulation of a low-power, high-performance Radix-4 Booth Multiplier with an 8-bit width. The multiplier incorporates a preencoding mechanism to optimize the Booth encoding process, resulting in efficient multiplication suitable for digital signal processing applications.

*Note: Project still under construction.*

## Contents
- [Project Overview](#project-overview)
- [Block Diagram](#block-diagram)
- [Circuit Diagram](#circuit-diagram)
- [Specifications](#specifications)
- [Performance Parameters](#performance-parameters)
- [Tools Used](#tools-used)
- [Installation](#installation)
  - [Ubuntu Installation](#ubuntu-installation)
  - [Windows Installation](#windows-installation)
- [Pre-Layout Schematic and Simulations](#pre-layout-schematic-and-simulations)
- [Contributors](#contributors)
- [Acknowledgments](#acknowledgments)
- [Contact Information](#contact-information)

## Project Overview
The Radix-4 Booth Multiplier with preencoded mechanism is designed to reduce the number of partial products in multiplication, optimizing both speed and power. This project includes the schematic and simulation of the multiplier design. The preencoding mechanism helps in simplifying the Booth encoding, making it more suitable for VLSI implementations.

A multiplier circuit is a fundamental component in digital signal processing (DSP) and machine learning applications, where power efficiency and speed are critical for performance. The Low-Power Radix-4 Booth Multiplier with Pre-Encoded Mechanism leverages the radix-4 Booth algorithm to reduce partial products, minimizing switching activities and thus lowering power consumption. This design is especially relevant in power-sensitive applications such as digital processors, DSP systems, and mobile devices where high efficiency is paramount. Careful design is required to ensure low power dissipation without compromising computation accuracy.

The principle of operation, implementation, issues and improvements, conclusion, and future scope will be discussed further.

**Upload your paper on Github and give a link to it**


## Block Diagram

 <p align="center">
  <img width="800" height="500" src="/Images/N/block.png">
</p>


## Circuit Diagram

 <p align="center">
  <img width="800" height="500" src="/Images/N/circuit.png">
</p>

## Specifications

| Specification       | Value      |
|---------------------|------------|
| Multiplier Width    | 8 bits     |
| Power Supply (VDD)  | 1.8V       |
| Technology          | 130nm CMOS |

## Performance Parameters

| Parameter                  | Description                            | Value     | Unit      |
|----------------------------|----------------------------------------|-----------|-----------|
| Power Consumption          | Average power dissipation             | TBD       | mW        |
| Delay                      | Maximum propagation delay             | TBD       | ns        |
| Area                       | Total area of multiplier              | TBD       | µm²       |
| Frequency                  | Maximum operating frequency           | TBD       | MHz       |


| Parameter| Description| Min | Type | Max | Unit | Condition |
| :---:  | :-: | :-: | :-: | :---:  | :-: | :-: |
|Technology| 0.18 µm CMOS Process |
|RL|Load resistance at Vbgp terminal | 100|||Mohm|VDD=3.3V, T=27C|
|CL|Load capacitance at Vbgp terminal|||50|pF|VDD=2.7V - 3.6V, T=-40C - 125C, RL=100M|
|Vbgp|Output Reference voltage|1.2013 |1.2056|1.2070|V|T=-40 to 140C, VDD=3.3V|
|Vbgp|Output Reference voltage|1.1698 |1.2056|1.2234|V|VDD=2.7V to VDD=3.6V, T=27C|
|TC_vbgp|Temperature Coefficient of Vbgp||26.2663||ppm/C|T=-40 to 125C, VDD=3.3V|
|VC_vbgp|Voltage Coefficient of Vbgp||5.9555||%/V|VDD=2.7V to 3.7, T=27C|
|Tstart|Start up time||3.3||us|Vdd=3.3V, T=27C, CL=50pF|
|VDD|Supply Voltage|3.2|3.3|3.6|V|T=-40C to 125C|
|IDD|Supply Current||22.4760||uA|EN=1|
|IDD|Supply Current||95.3950||pA|EN=0|

## Tools Used
- **eSim**: Free/libre and open-source EDA tool for circuit design, simulation, and PCB design.
- **Ngspice**: Open-source SPICE simulator for electric and electronic circuits.
- **SkyWater Open Source PDK**: Open-source Process Design Kit for 130nm CMOS technology.

## Installation

### Ubuntu Installation
1. Update your package list:
   ```bash
   sudo apt-get update

### eSim Installation
Refer to the following link for eSim installation, which includes Ngspice and Sky130nm PDK:
eSim Installation Guide





## Pre-Layout Performance Characteristics

###  Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_temp.png">
</p>


###  Vbgp v/s VDD [ 2V - 4V] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_supply.png">
</p>

###  Temperature Coefficient of Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_tc.png">
</p>

###  Voltage Coefficient of Vbgp v/s VDD [ 2V - 4V] @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_vc.png">
</p>

###  Start-Up Time of Vbgp @ RL = 100M ohms plot


 <p align="center">
  <img width="800" height="500" src="/Images/N/PRE/pre_startup.png">
</p>


###  On-Off-Current of Vbgp wrt Enable @ RL = 100M ohms plot

 <p align="center">
  <img width="1000" height="500" src="/Images/N/PRE/pre_c.png">
</p>

**Note: Current without Inverter for Enable Logic**



## Tools used and steps to reproduce all waveforms (Tools allowed are xschem/eSim/ngspice) 
Ngspice is an open source mixed-signal circuit simulator.

### Installing Ngspice

#### For Ubuntu

Open your terminal and type the following to install Ngspice
```
$  sudo apt-get install -y ngspice
```

## Running the Simulation


To enter the Ngspice Shell, open the terminal & type:
```
$ ngspice
```
To simulate a netlist, type:
```
ngspice 1 ->  source <filename>.cir
```

You can exit from the Ngspice Shell by typing:
```
ngspice 1 ->  exit
```
 <p align="center"> or </p>
 
```
ngspice 1 ->  quit
```

There are several waveforms that need to be obtained to observe the performance of the Bandgap reference circuit.

### Pre-Layout Simulation

To clone the Repository and download the Netlist files for Simulation, enter the following commands in your terminal.

```
$  sudo apt install -y git
$  git clone https://github.com/sherylcorina/avsdbgp_3v3
$  cd avsdbgp_3v3/Simulation/Ngspice_Simulation/Final_Simulation/PreLayout
```




### To obtain the Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot


Run the netlist file using the following command.
```
$  ngspice pre_temp.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_temp.png">
</p>


### To obtain the Vbgp v/s VDD [ 2V - 4V ] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice pre_supply.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_supply.png">
</p>

### To obtain the Temperature Coefficient of Vbgp v/s Temperature [ -40C - 140C] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice pre_tc.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_tc.png">
</p>

### To obtain the Voltage Coefficent of Vbgp v/s VDD [ 2V - 4V ] @ RL = 100M ohms plot

Run the netlist file using the following command.
```
$  ngspice pre_vc.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_vc.png">
</p>

### To obtain the Start Up Time plot


Run the netlist file using the following command.
```
$  ngspice pre_startup.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_startup.png">
</p>


###  On-Off-Current of Vbgp wrt Enable [1 -> 0] @ RL = 100M ohms plot


Run the netlist file using the following command.
```
$  ngspice pre_enable.cir
```
 <p align="center">
  <img width="800" height="500" src="/Images/PS/pre_ps_startup.png">
</p>

**Note: Current without Inverter for Enable Logic**

***************



## Future Work

1. 

## Contributors 

- **Kunal Ghosh** Director, VSD Corp. Pvt. Ltd.
- **Sumanto Kar** Assistant Project Manager, FOSSEE

## Acknowledgments

- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.

## Contact Information

- Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com
