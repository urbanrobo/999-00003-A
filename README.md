# 999-00003-A: On-Board Computer (OBC) Requirements Document

Halo Car Inc uses a modified [US government design review process](https://en.wikipedia.org/wiki/Design_review_(U.S._government)) to design, fabricate, and distribute the  Kia Niro (KN) Series of cars.  This will aid in keeping the product within budget, on time, and limit requirement creep. All tasks and timelines will be tracked using [Linear](https://linear.app/halocar), Fusion 360 3D CAD models [Cloud Team Server](https://halo5.autodesk360.com/g/all_projects/active), business data stored in an organized [Halo_ALL](https://drive.google.com/drive/u/0/folders/0AKq4yLznZ1RzUk9PVA) Google Drive folder, and ALL other engineering data stored in multiple [Halo Hardware Github](https://github.com/orgs/urbanrobo/teams/hardware/repositories) repos.

**Future cars like Chevy Bolt and Tesla Model 3 shall only follow these requirements, if specifically called out in this document.**

AUTHOR(S): BLAZE SANDERS, YASH SHAH

APPROVED BY: ANAND NANDAKUMAR ON 2023-03-??-1300


## 1.0 Mission Concept Review (MCR)
See [Bill Of Material]() and [Halo Pitch Deck](???) and [999-00001-A Kira Niro System Architecture Requirements Document](https://docs.google.com/document/d/1RNme7q0ufrCDHNyr7VOxuHKhVUad4LDPr4K3CM-rN78/edit) 

<br> Objectives:
1. Allow any EV with ISO 11898-2 high-speed CAN Bus interface (1 Mbit/s on CAN, 5 Mbit/s on CAN-FD) to be remote piloted via 5G cellular.
2. Create a multipiece computer case with [IP50](https://reactual.com/portable-electronics/understanding-ip-code.html) rating, good airflow (internal to case), and great stress relief on all cables.
3. Installation of standby OBCs should be extremely easy/fast and have low risk of breaking cable harnesses. 
4. Create rental fleet of 10 stacked vehicles by April 15 that could be resold to dealerships for less than $2k in repairs.                                                

<br> Concepts to meet Objectives:
1. Analog man in the middle attack and digital CAN Bus reverse engineering. 
2. A three piece metal case (external box provide cable stress relief, internal box holds components, and top lid protects against dust).
3. The insertion on an internal box into an external box that never leaves vehicle should take less than 15 minutes and reduce cable bend cycles.
4. All hardware alternations must limit the number of holes put into a vehicle and not damage paint in all way long term. <br> <br>

## 2.0 Mission Definition Review (MDR
All hardware and software requirements must be described in metric units (kg & cm)
### 2.1 Hardware V1 Functional Requirements:
1. Branding:
   * 1.1 - KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all hardware PCB’s and vehicle vinyl wraps.
   
2. Printed Circuit Boards
   * 2.1 - All PCB installed into the KN Series of vechiles shall be conformal coated 
   * 2.2 - All PCB's shall use this [Halo PCB Altium Project Template](https://github.com/jose-halocar/ee_altium_template/blob/master/HaloCar_Project_Rename_This_File.PrjPcb)
     * DESIGN NOTE: Specs like four layer stackup, copper weight, and drawing title block are defined here
   * 2.3 - Schematics:
     * 2.3.1 - Custom Halo dataloggers shall use the [STM32G4](https://www.st.com/en/microcontrollers-microprocessors/stm32g4-series.html) family of microcontrollers.
   * 2.4 - PCB Layouts:

3. Motherboard Subsytem:
   * 3.1 - There shall be clean and quick (less than 1 minute) access to coin cell battery.
     * DESIGN NOTE: For replacement of battery after normal usage and to clear memory to fix [Q-Code](https://www.asus.com/support/FAQ/1043948/) errors.

4. Cables Harnesses:
   * 4.1 - USB 2.0
   * 4.2 - GPS SMA Coxial
   * 4.3 - Cellualar SMA Coxial Cable
   * 4.4 - Analog Voltage Cables
     * 4.4.1 - All analog inputs into microcontrollers shall have local hardware based low pass filters.
       * Design Note: Cut off frequency determined based on real life Electromagnetic Interference (EMI) samples from a 6 GHz oscilloscope. 
   * 4.5 - CAN Bus 

5. Analog 

6. Production Part Database cost per KN shall be less than $4K 

Spheriecal vibration isolatorin in each direction 
11K RPM server fans https://www.youtube.com/watch?v=nAFB9w2Rh0Y

### 2.2 Software V1 Functional Requirements:
1. Branding:
   *1.1 KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all software.


### 3.0 Dependency / Requirement Traceability Matrix:


### 4.0 Tracked Hardware / Software Issues:
1. See software bugs in LINEAR???
2. See hardware bugs at https://github.com/urbanrobo/OBC/issues

### 5.0 Project Management
See https://linear.app/halocar/team/HW/active

### 6.0 Free Form Scrath Pad for Hardware & Software V2 Requirements
