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

## Design 
### Box

### PCB 
We choose ROGERS<sup>TM</sup> 4003C as the PCB material which has a typical relative dielectric constant of 3.55. Given a thickness of 0.508 mm, the track and gap widths are chosen as 0.9 mm and 0.3 mm, respectively, for achieving an 50 $\Omega$ characteristic impedance. This track width is convenient for soldering the SMA connectors. We also added 0.25 mm-diameter vias with 1 mm separation to improve the high-frequency performance of the GCPW.

\* The calculation of characteristic impedance is made by MWI Calculator provided by ROGERS<sup>TM</sup>* [see **RO4003C.png** for detail].

<img src="COMSOL/PCB_EM.png" alt="Preview" width="800"/>


## Mounting procedure:

## Acknowledgement:
We are delighted if you find this project helpful to your own study. Feel free to contact us if you have questions, suggestions, criticisms, etc. You are free to copy, share, and build on this project without notifying the authors. Citing our publications is appreciated but not required. 
