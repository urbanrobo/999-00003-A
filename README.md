# 999-00003-A: On-Board Compute (OBC) Requirements Document

Halo Car Inc uses a modified [US government design review process](https://en.wikipedia.org/wiki/Design_review_(U.S._government)) to design, fabricate, and distribute the  Kia Niro (KN) Series of cars.  This will aid in keeping the product within budget, on time, and limit requirement creep. All tasks and timelines will be tracked using [Linear](https://linear.app/halocar), Fusion 360 3D CAD models [Cloud Team Server](https://halo5.autodesk360.com/g/all_projects/active), business data stored in an organized [Halo_ALL](https://drive.google.com/drive/u/0/folders/0AKq4yLznZ1RzUk9PVA) Google Drive folder, and ALL other engineering data stored in multiple [Halo Hardware Github](https://github.com/orgs/urbanrobo/teams/hardware/repositories) repos.

**Future cars like Chevy Bolt and Tesla Model 3 shall only follow these requirements, if specifically called out in this document.**

AUTHOR(S): BLAZE SANDERS

APPROVED BY: ANAND NANDAKUMAR ON 2023-03-??-1300


## 1.0 Mission Concept Review (MCR)
See [Bill Of Material]() and [Halo Pitch Deck](???) and [999-00001-A Kira Niro System Architecture Requirements Document](https://docs.google.com/document/d/1RNme7q0ufrCDHNyr7VOxuHKhVUad4LDPr4K3CM-rN78/edit) 

<br> Objectives:
1. Allow any EV with ISO 11898-2 high-speed CAN Bus interface (1 Mbit/s on CAN, 5 Mbit/s on CAN-FD) to be remote piloted via 5G cellular.
2. Create a multi-piece computer case with [IP50](https://reactual.com/portable-electronics/understanding-ip-code.html) rating, good airflow (internal to case), and great stress relief on all cables.
3. Installation of standby OBCs should be extremely easy/fast and have low risk of breaking cable harnesses. 
4. Create rental fleet of 10 stacked vehicles by April 15 that could be resold to dealerships for less than $2k in repairs.                                                

<br> Concepts to meet Objectives:
1. Analog man in the middle attack and digital CAN-FD Bus read and write access.
2. A three piece metal case (external box provide cable stress relief, internal box holds components, and top lid protects against dust & customers).
3. The insertion on an internal box into an external box that never leaves a vehicle should take less than 15 minutes and reduce cable bend cycles.
4. All hardware alternations must limit the number of holes put into a vehicle and not damage paint in ANY way long term. <br> <br>

## 2.0 Mission Definition Review (MDR)
All hardware and software requirements must be described in metric units (kg, cm, and degrees Celsius)

### 2.1 Hardware V1 Functional Requirements:
1. Branding:
   * 1.1 - KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all hardware PCB’s, anodized aluminum, and vehicle vinyl wraps.
   * 1.2 - Clean cable management of all wires 
   
2. Printed Circuit Boards
   * 2.1 - All PCB's installed into the KN Series of vehicles shall be conformal coated. 
   * 2.2 - All PCB's shall use the [Halo PCB Altium Project Template](https://github.com/jose-halocar/ee_altium_template/blob/master/HaloCar_Project_Rename_This_File.PrjPcb)
     * DESIGN NOTE: This template defines specs like four layer stackup, copper weight, and drawing title block are defined here
   * 2.3 - Schematics:
     * 2.3.1 - Custom Halo data loggers shall use the [STM32G4](https://www.st.com/en/microcontrollers-microprocessors/stm32g4-series.html) family of microcontrollers.
   * 2.4 - PCB Layouts:

3. Data Processing Subsystems:
   * 3.1 - There shall be clean and quick (less than 1 minute) access to coin cell battery on selected motherboard.
     * DESIGN NOTE: For replacement of battery after normal usage and to clear memory to fix [Q-Code](https://www.asus.com/support/FAQ/1043948/) errors.
   * 3.2 - The vehicle Chassis CAN (C-CAN) and Powertrain CAN (P-CAN) shall interface with the OBC via a PCI Express slot.
   * 3.3 - The On-Board Compute and vehicle ignition start/stop line shall have the ability to be powered on by a Radio Frequency (RF) button click.

4. Cables Harnesses:
   * 4.1 - All USB 2.0 cables for cameras shall be less then ?2.5 meters?, contain ground shielding, and have impedance controlled twisted pairs. 
   * 4.2 - All GPS antenna cables shall be less then ?1.5 meters? and coaxial cables with SMA connectors.
   * 4.3 - All cellular antenna cables shall be less then ?1.5 meters? and coaxial cables with SMA connectors.
   * 4.4 - All wires carrying analog voltage for control surfaces (e.g. brake & gas pedal) shall be less than 1 meter and multi-stranded.
     * 4.4.1 - All analog inputs into microcontrollers shall have local hardware based low pass filters.
       * Design Note: Cut off frequency determined based on real life Electromagnetic Interference (EMI) samples from a 6 GHz oscilloscope. 
   * 4.5 - All CAN Bus cables shall be less then 5 meters and ??? 

5. Security:
   * For legal / IP reasons is shall be clear that customers are not allowed to touch hardware.
   * The internal OBC box shall have "Do Not Taper" stickers.
     * DESIGN NOTE: [EXAMPLE STICKER THAT MAY CHANGE](https://www.grainger.com/product/38E801?gucid=N:N:PS:Paid:GGL:CSM-2295:4P7A1P:20501231&gclid=Cj0KCQiAutyfBhCMARIsAMgcRJR3yioMc0_DuhTHmW255EtnDVs2-LeNE-f4x5XzFgfv-0M7RsnVqO4aAo7JEALw_wcB&gclsrc=aw.ds)
   * The external OBC box shall have "Do Not Taper: Doing so means immediate removal from the Halo rental platform"  text etched into metal  
   * The OBC lid shall have two 4 digit pin based locking systems.
   * The OBC lid shall have four locking bolts that require special tools to loosen.
   * The OBC shall contain NO source code, with as few binary executables as possible (goal is one).
   * The OBC login and SSH ports shall be protected by only passwords (not SSD encryption or a Data Loss Prevention (DLP) security strategy).    

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
