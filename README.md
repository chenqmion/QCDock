<img src="QCD_Box.PNG" alt="Preview" width="800"/>

# QCD Box
This repository contains the **design files** and **simulation files** of an 8-port sample box designed for 10x10 mm chips.

## Related works:

## Description
### Design files in SOLIDWORKS<sup>TM</sup>
* **BOX.SLDASM** is the final assembly of the sample box.
* **BOX_A.SLDASM** and **BOX_B.SLDASM** are the box and the lid, respectively.
* **PCB.SLDASM** is the PCB with GCPW-type transmission lines.
* **Chip.SLDASM** is a fake 10x10 mm chip for consistency check of the geometry.
* **SMA.SLDASM** is a fake SMA connector for consistency check of the geometry.

\* For non-SOLIDWORKS users, you can check the geometry from the corresponding **.step** files.

### Simulation files in COMSOL<sup>TM</sup>
* **Box_eigenmode.mph** simulates the box mode around 10 GHz. The lowest eigenfrequency is found at 12.17 GHz.
* **PCB_frequencydomain.mph** simulates the scattering coefficients and the input impedance of the PCB ports. 

## Box design 
### Cavity
Given that the sample box will normally work in the DC -- 8GHz range, we should minimize the box size to push the first box mode as high as possible. The flange size of the SMA connectors determines the outer height of the box as 13 mm, as well as the thickness of the side wall as 4 mm. The inner width of the box is chosen as 21 mm, which will leave a space of 6 mm for wire bounding, assuming that an 10x10 mm chip is used.

It is useful to have an empty space in the lid to push the first box mode to an even higher frequency. The size of the empty box should be half of the cavity size, saying 10.5x10.5 mm, while the height is not crucial (we choose 4.3 mm). 

We also designed an empty space below the chip to (i) push the bottom ground further way to simplify the circuit design, and (ii) push the chip mode to a higher frequency. The box size is 9x9x3.2 mm in our design, leaving an 0.5 mm distance from the edge to mechanically support the chip.

In the end, we designed fillet to the box to avoid concentration of EM fields at the corners.

### SMA connectors
To achieve the best impedance match between the SMA connectors and the PCB with minimum efforts, we choose the panel-mount connectors with flat pin. There are only several products of this type available in the market. We choose the M54FM0112F07C model from Micro RF Connector, which has an 0.8mm-diameter 4mm-long impedance-matched extension that can be conveniently inserted into the box. The extruded pin is 0.8mm-wide and 1.5mm-long, which will determine the launch pad design of the PCB. 

\* This connector is likely not non-magnetic.

### Mounting holes
The box and the lid is assembled with 9 x M2.5 screws that are evenly spaced on the side walls. Owing to the compact size, the corresponding holes are designed as through holes to be mutiplexed for mounting the sample box to the cryostat. 

\* A dedicated mounting plate can be used if necessary.

The PCB is mounted inside the cavity via 4 x M2 screws with a length of 3mm. Brass may be a good choice of these screws as they provide strength as well as electrical and thermal condictivities.

\* Silver paste can be used to improve the electrical and thermal conductivity between the PCB and the box.

### Simulation results
<img src="COMSOL/Box_EM.png" alt="Box mode" width="800"/>

## PCB design
### GCPW parameters
We choose ROGERS<sup>TM</sup> 4003C as the PCB material which has a typical relative dielectric constant of 3.717. Given a thickness of 0.508 mm, the track and gap widths are chosen as 1 mm and 0.64 mm, respectively, for achieving an 50 $\Omega$ characteristic impedance. This track width is convenient for soldering the SMA connectors. 

The wire bounding between the PCB and the chip may prefer an approximately matched size between the GCPW and the launcher. We change the track and gap widths into 0.6 mm and 0.11 mm after 2.2 mm from the edge, where an 0.7 mm-long gradual change is designed to connect the two geometries.

We also added 0.25 mm-diameter vias with 1 mm separation to improve the high-frequency performance of the GCPW.

\* The calculation of characteristic impedance is made by MWI Calculator provided by ROGERS<sup>TM</sup>* [see **RO4003C.png** for detail].

### Simulation results
<img src="COMSOL/PCB_EM.png" alt="PCB mode" width="800"/>

<img src="COMSOL/PCB_S.png" alt="S parameters" width="800"/>

<img src="COMSOL/PCB_Z.png" alt="Impedance" width="800"/>

## Mounting procedure:

## Acknowledgement:
We are delighted if you find this project helpful to your own study. Feel free to contact us if you have questions, suggestions, criticisms, etc. You are free to copy, share, and build on this project without notifying the authors. Citing our publications is appreciated but not required. 
