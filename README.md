# FinFET-Circuit-Design-and-Characterization

This repository contains the whole summary of the hands-on work done by Abhinav Prakash during the workshop on Packaging Fundamentals and testing. The workshop offered an in-depth exploration of the semiconductor packaging process, covering essential principles, the progression of packaging technologies, and cutting-edge 2.5D/3D architectures. It delved into interconnect methods, redistribution layers (RDLs), interposers, assembly techniques, and package reliability assessments. Participants also gained practical experience through hands-on sessions involving thermal simulations, package design, and modeling using ANSYS tools.

## *Table of Contents*

* [Module 1: Scaling Beyond CMOS: FinFET Devices and Innovations](#Module-1)
    + [Evolution of CMOS Technology](#Evolution-of-CMOS-Technology)
    + [Reason for Using FinFETs](#Reason-for-Using-FinFETs)
    + [Impact on Circuit Performance: Tri-Gate vs Planar Transistors](#Impact-on-Circuit-Performance-Tri-Gate-vs-Planar-Transistors)
    + [CMOS Technology Scaling](#CMOS-Technology-Scaling)
    + [Standard Cell area Scaling](#Standard-Cell-area-Scaling)
    + [Parasitic Resistance](#Parasitic-Resistance)
   
   
    
* [Module 2: Lab-to-Simulation: 7nm FinFET Inverter Performance Analysis](#Module-2)
    + [Overview of Supply Chain and Assembly Facilities](#Overview-of-Supply-Chain-and-Assembly-Facilities)
    
   
 
* [Module 3: Designing Bandgap References Using 7nm FinFETs](#Module-3)
    + [Introduction With ANSYS Electronics Desktop](#Introduction-With-ANSYS-Electronics-Desktop)
    + [Lab1-Designing Flip-Chip BGA Package](#Lab1-Designing-Flip-Chip-BGA-Package)
  
          

 

* [Appendix](#Appendix)
* [References](#references)
* [Acknowledgement](#acknowledgement)
* [Accreditation](#Accreditation)
* [Inquiries](#inquiries)


## Module 1:
## Scaling Beyond CMOS: FinFET Devices and Innovations
---
### Evolution of CMOS Technology
---
The evolution of CMOS (Complementary Metal-Oxide-Semiconductor) technology is driven by the need for enhanced performance, energy efficiency, and scalability toward the 1nm node and beyond. This progression encompasses multiple innovation domains:

- Channel Materials: Transitioning from traditional silicon to 2D materials like MoS₂, offering superior electrostatic control and scalability.
- Patterning Techniques: Advancements in lithography, moving from ArF and KrF to EUV and High NA EUV, enable finer feature sizes and improved pattern fidelity.
- Interconnection Materials: Emerging materials such as Ruthenium (Ru) and topological semimetals are being explored to reduce resistance and improve signal integrity.
- Gate Stack Materials: Novel transistor designs like NC-FETs and TFETs with dipole high-k metal gates (HKMG) are being developed to lower power consumption and enhance switching performance.
- Device Structures: Innovations include VFETs, 3DS-FETs, and FinFETs, which offer better density and performance scaling.
- DTCO (Design Technology Co-Optimization): Techniques like Backside Illumination (BSI) optimize layout and performance.
- STCO (System Technology Co-Optimization): Chiplet architectures enable modular integration and system-level efficiency.

<img width="1620" height="712" alt="Screenshot 2025-08-27 151702" src="https://github.com/user-attachments/assets/1e345710-0b9a-4004-b236-c33cffb59a7e" />



### Reason for Using FinFETs 
---
FinFETs (Fin Field-Effect Transistors) are a key advancement in transistor design, addressing limitations of traditional planar transistors. Their 3D structure allows the gate to wrap around the channel, offering better electrostatic control and reducing sub-channel leakage. Compared to planar designs, FinFETs:

- Enhance gate capacitance via multi-gate configurations.
- Reduce drain capacitance due to undoped channels.
- Improve short-channel performance, critical for scaling down to advanced nodes.
- Decouple width Ion from transistor area, enabling higher drive current without increasing footprint.
  
These features make FinFETs ideal for high-performance, low-power applications in modern CMOS technology.

<img width="1642" height="869" alt="Screenshot 2025-08-27 153850" src="https://github.com/user-attachments/assets/6e1dce3f-341b-4a94-945a-8cfde9e1ecf6" />

### Impact on Circuit Performance: Tri-Gate vs Planar Transistors
---
Tri-Gate transistors offer significant advantages over traditional Planar transistors in terms of leakage control and drive strength:

- **Lower Leakage Current:** As shown in the left graph, Tri-Gate transistors exhibit a lower off-current at the same on-current. This translates to reduced power dissipation, making them ideal for energy-efficient designs.
- **Higher Drive Current:** The right graph demonstrates that Tri-Gate transistors can achieve a higher drive current at the same off-current compared to Planar devices. This results in faster switching speeds and enhanced circuit performance.

Overall, the Tri-Gate architecture improves electrostatic control, enabling better scalability and performance in advanced CMOS nodes.
<img width="1398" height="718" alt="Screenshot 2025-08-27 160241" src="https://github.com/user-attachments/assets/c3846d0c-8b9c-4fc4-9ddf-9679f03ce595" />

### CMOS Technology Scaling
---
CMOS scaling has evolved from planar transistors to advanced 3D and 2D architectures, driven by the need for higher performance, lower power, and reduced leakage. Early nodes introduced voltage scaling and copper interconnects, followed by strained silicon and high-k metal gates to enhance mobility and control. FinFETs emerged at 22 nm, enabling better electrostatics, while extreme ultraviolet (EUV) lithography supported further miniaturization at 7 nm and below. Recent nodes feature Gate-All-Around (GAA) and stacked CFETs, with 2D materials like MoS₂ promising future breakthroughs. Cell designs have been optimized for density, speed, and voltage, and transistor structures now integrate high-mobility channels and novel gate configurations to sustain Moore’s Law.

- Voltage Scaling (180 nm): Reduced supply voltage to lower power consumption and heat generation.
- Copper Interconnects (130 nm): Replaced aluminum with copper for better electrical conductivity.
- Strained Silicon (90 nm): Applied strain to silicon to enhance carrier mobility and speed.
- SiGe & ULK Materials (65 nm): Used silicon-germanium and ultra-low-k dielectrics to reduce delay.
- High-k Metal Gate (45 nm): Introduced high-k dielectrics and metal gates to reduce leakage and improve control.
- Raised Source/Drain (32 nm): Boosted drive current using raised source/drain structures with HKMG.
- FinFET Technology (22 nm): Enabled better electrostatic control with 3D fin-shaped transistors.
- Advanced Patterning (14–10 nm): Used complex multi-patterning techniques for finer transistor features.
- EUV Lithography (7–5 nm): Adopted extreme ultraviolet light for precise and scalable fabrication.
- SiGe Fin PMOS (5 nm): Enhanced PMOS performance using silicon-germanium fin structures.
- Gate-All-Around (3–1.4 nm): Improved gate control with all-around gate wrapping the channel.
- CFET & 2D FET (Sub-1 nm): Used stacked complementary FETs and 2D materials like MoS₂ for ultra-scaling.
- High Density Cell (0.092 µm²): Compact design with 1 pass gate and 1 pull down for space efficiency.
- Low Voltage Cell (0.108 µm²): Optimized for low voltage with 1 pass gate and 2 pull downs.
- High Speed Cell (0.130 µm²): Designed for speed with 2 pass gates and 3 pull downs.
- Planar vs Tri-Gate vs Leakage: Tri-gate and leakage-reduced designs offer better current control.
- High Mobility Channels: Materials like MoS₂ outperform silicon in drive current at scaled nodes.
- Future Layouts: Include stacked P-over-N and contact-over-active designs for post-2028 scaling.

<img width="1549" height="763" alt="Screenshot 2025-08-28 114410" src="https://github.com/user-attachments/assets/dcea79e5-3eea-461c-bf7b-c44f6148c70e" />

<img width="1676" height="790" alt="Screenshot 2025-08-28 114538" src="https://github.com/user-attachments/assets/d647e446-8afd-4734-9755-57a2bb7cdcb9" />

### Standard Cell area Scaling
---
Standard cell area scaling in Samsung’s advanced nodes—from 10nm to 5nm—demonstrates progressive reductions in both width and height by optimizing Contacted Poly Pitch (CPP) and fin count. The 10nm node features a 204 nm width and 420 nm height with 10 fins, while the 5nm node maintains a 162 nm width but reduces height to 216 nm with 8 fins. These refinements enable higher transistor density, improved performance, and more efficient power usage in modern semiconductor designs.

<img width="1421" height="705" alt="Screenshot 2025-08-28 161703" src="https://github.com/user-attachments/assets/c4757cac-36d6-4e7f-a92d-7958fca75891" />

- Double Diffusion Break (DDB): Used to isolate adjacent transistors, but consumes more area.
- Single Diffusion Break (SDB): Reduces cell width by minimizing isolation space between transistors.
- Contact Over Field Gate (COFG): Enables tighter layout by placing contacts over field gates.
- Contact Over Active Gate (COAG): Further shrinks area by allowing contacts directly over active gates.
- X-axis and Y-axis Scaling: Achieved through layout optimizations to reduce both width and height of cells.
- 6-Track Tall Cell: Standard cell height defined by six metal tracks, balancing density and routing.
- Front-side vs Back-side PDN: Back-side power delivery improves routing efficiency and reduces congestion.
- Microscopic Views: Show structural differences between DDB and SDB, and NMOS cell configurations.
- Cell Height Optimization: Includes power rail (PVR) and ground (GND) alignment for compact design.

<img width="1567" height="748" alt="Screenshot 2025-08-28 161716" src="https://github.com/user-attachments/assets/f8c2bbc9-a820-4da6-be52-04d5174a7ad3" />

### Parasitic Resistance
--- 

- Planar MOSFET: Has a parasitic resistance ratio <1, indicating low external resistance relative to channel resistance.
- FinFET: Shows a balanced ratio =1, meaning external and channel resistances are comparable.
- GAA FET: Exhibits a higher parasitic resistance ratio ∼3, due to reduced contact width relative to gate width.
- CFET: Also has a high parasitic resistance ratio ∼3, similar to GAA, reflecting challenges in contact scaling.

<img width="1587" height="839" alt="Screenshot 2025-08-28 161800" src="https://github.com/user-attachments/assets/cd0ba12b-5d64-40d9-aef0-ce0e46986338" />

## Module 2:
## Lab-to-Simulation: 7nm FinFET Inverter Performance Analysis
---
### 
---


## Module 3:
## Designing Bandgap References Using 7nm FinFETs
---
### 
---

## References
---




## Acknowledgement
---
Finally, I would like to express my sincere gratitude to [Kunal Ghosh](https://www.linkedin.com/in/kunal-ghosh-vlsisystemdesign-com-28084836/){Co-founder of VLSI System Design (VSD) Corp. Pvt. Ltd.} and Tarun Kumar Agrawal {Dept. of Electrical Engineering IIT Gandhinagar}   for help me in understanding the Packaging - Fundamentals-and-testing. The workshop was excellent and well-designed, this workshop taught about Packaging Design and Techniques 

## Accreditation
---
- To be Added ...!

## Inquiries
---
- Connect with me at [LinkedIn](https://www.linkedin.com/public-profile/settings?trk=d_flagship3_profile_self_view_public_profile)
