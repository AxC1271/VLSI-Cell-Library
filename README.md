# Repository for VLSI Projects
Hi there! Welcome to my repository on VLSI, where I explore chip design, layout, simulation, and verification using open source tools like Magic, ngspice, netgen, and Xschem. After taking a digital systems design course at Case, I felt a huge amount of interest in chip design but felt frustrated due to the fact that there were very limited resources online. This repository is a portfolio of the projects that I've undertaken as a result of my curiosity and initiative to learn something like CMOS chip design and I hope for anyone reading this to find my repository not only a proof of my skills and knowledge but also as an inspiration for those interested going into chip design but have no idea where to start. I aim to make my README's as informative and educational without being didactic to my intended audience (employers and other ECSE students).

# Questions about my Tools
All of the following tools were installed on my Ubuntu VM using apt-get install commands. If you have any personal questions about setting up please contact me at achen5291@gmail.com as I would love to help out and spread my passion for chip design.

## Xschem
This is the schematic software that I use to draw out transistor networks and often provides me the visual picture that I need to see what circuit I am designing/testing. 

## Magic VLSI Layout
Magic is the physical layout tool where you put your n-diffusion layers, p-diffusion layers, polysilicon, etc. to form your MOSFETs. Magic also provides a command prompt to convert your layout to a spice netlist.

## netgen
For those unfamiliar, netgen does an LVS check (layout vs. schematic) to ensure that the physical layout on Magic models exactly what the intended schematic is meant to do. This is just a safety check to ensure that you don't produce faulty chips from your layout.

## ngspice
ngspice is used to simulate the spice netlist from Magic using a spice directive. 

## Technology Node
As for the specific transistor model I am using, it's on the website <a>http://www.opencircuitdesign.com/magic//</a> and the model I am using currently is the 2002a (although this may change to the sky130A pdk in the future). 

# Projects So Far

## 1. CMOS Inverter
