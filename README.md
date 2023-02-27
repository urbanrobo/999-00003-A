# 999-00003-A: On-Board Compute (OBC) Requirements Document

Halo Car Inc uses a modified [US government design review process](https://en.wikipedia.org/wiki/Design_review_(U.S._government)) to design, fabricate, and distribute the  Kia Niro (KN) Series of cars.  This will aid in keeping the product within budget, on time, and limit requirement creep. All tasks and timelines will be tracked using [Linear](https://linear.app/halocar), Fusion 360 3D CAD models [Cloud Team Server](https://halo5.autodesk360.com/g/all_projects/active), business data stored in an organized [Halo_ALL](https://drive.google.com/drive/u/0/folders/0AKq4yLznZ1RzUk9PVA) Google Drive folder, and ALL other engineering data stored in multiple [Halo Hardware Github](https://github.com/orgs/urbanrobo/teams/hardware/repositories) repos.

**Future cars like Chevy Bolt and Tesla Model 3 shall only follow these requirements, if specifically called out in this document.**

AUTHOR(S): BLAZE SANDERS

APPROVED BY: ANAND NANDAKUMAR ON 2023-03-??-1300


## 1.0 Mission Concept Review (MCR)
See [Bill Of Material]() and [Halo Pitch Deck](?TODO?) and [999-00001-A Kira Niro System Architecture Requirements Document](https://docs.google.com/document/d/1RNme7q0ufrCDHNyr7VOxuHKhVUad4LDPr4K3CM-rN78/edit) 

<br> Objectives:
1. Allow any EV with ISO 11898-2 high-speed CAN Bus interface (1 Mbit/s on CAN, 5 Mbit/s on CAN-FD) to be remote piloted via 4G LTE cellular connection.
2. Create a multi-piece computer case with [IP62](https://reactual.com/portable-electronics/understanding-ip-code.html) rating, good airflow, and great stress relief on all cables.
3. Enable installation of standby OBCs should be extremely easy / fast (less than 15 minutes) and have low risk of breaking cable harnesses. 
4. Create rental fleet of 9 stacked KN vehicles and ??? CB vehicles by April 15 that could be resold to dealerships for less than $2k in repairs.                                                

<br> Concepts to meet Objectives:
1. Analog man in the middle attack and digital CAN-FD Bus read and write access.
2. A three piece metal case (200-0001-A): Consisting of an External Box (201-0001-A) that provides cable stress relief and mounting points for fans & heat sinks while protecting against dust & small water drops; an Internal Box (201-0002-A) that holds components; and a Lid (201-0003-A) that protects against customer tamper and falling objects.
3. The insertion on an Internal Box (201-0002-A) into an External box (201-0001-A) which never leaves a vehicle thus limiting cable bend and insertion cycles to less than 3.
4. All hardware alternations must limit the number of holes put into a vehicle and not damage paint in ANY way long term. <br> <br>

## 2.0 Mission Definition Review (MDR)
All hardware and software requirements must be described in metric units (kg, cm, and degrees Celsius)

### 2.1 Hardware V1 Functional Requirements:
1. Branding:
   * 1.1 - KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all hardware PCB’s, anodized aluminum, and vehicle vinyl wraps.
   * 1.2 - No wires shall be visible to the customer outside and/or above the locking carpeted truck cover for customers to cut or play with.
   * 1.3 - All wires visible under the locking carpeted truck cover shall have kevlar covers to INCREASE cutting difficulty.
   * 1.4 - The External Box (201-0001-A) and Lid (201-0003-A) shall be bent anodized 5052 aluminum sheet metal of color Blue (0x2342F5).
   * 1.4 - The Internal Box (201-0002-A) shall be bent and NOT anodized 5052 aluminum sheet metal.   
   
2. Printed Circuit Boards
   * 2.1 - All PCB's installed into the KN Series of vehicles shall be conformal coated. 
   * 2.2 - All PCB's shall use the [Halo PCB Altium Project Template](https://github.com/jose-halocar/ee_altium_template/blob/master/HaloCar_Project_Rename_This_File.PrjPcb)
     * DESIGN NOTE: This template defines specs like four layer stackup, copper weight, and drawing title block are defined here
   * 2.3 - Schematics:
     * 2.3.1 - All Halo temperature and vibration data loggers shall use the [STM32G4](https://www.st.com/en/microcontrollers-microprocessors/stm32g4-series.html) family of microcontrollers.
     * 2.3.2 - All passive components (resistors, capacitors, inductors, crystals, etc) shall have at least an AEC-Q200 automotive [GRADE 1](https://www.golledge.com/news/the-aec-q200-standard-what-does-it-really-mean/#:~:text=The%20AEC%2DQ200%20qualification%20is,tests%20contained%20within%20the%20standard.) rating to survive temperatures of -40 to +125 °C.
      * DESIGN NOTE: An AEC-Q200 automotive [GRADE 0] range of -50 to +150°C would increase cost too much and over constrain vendor selection. 
   * 2.4 - PCB Layouts:
     * 2.4.1 - TODO

3. Data Processing Subsystems:
   * 3.1 - There shall be clean and quick (less than 1 minute) access to coin cell battery on the Crosshair VII motherboard (P/N TODO)
     * DESIGN NOTE: For replacement of battery after normal usage and to clear memory to fix [Q-Code](https://www.asus.com/support/FAQ/1043948/) errors.
   * 3.2 - The vehicle Chassis CAN (C-CAN) and Powertrain CAN (P-CAN) shall interface with the OBC via a M.2 slot.
   * 3.3 - Both the OBC power on/off and vehicle start/stop state shall be controllable by a Radio Frequency (RF) button click.
   * 3.4 - The OBC shall support 6 cameras at a resolution of 1080p 30 fps for FRONT Middle, REAR Left & REAR Right and 720p 30 fps for REAR, FRONT Left, and FRONT Right.
   * 3.5 - The GPS module shall use the motherboard USB 2.0 headers (not the USB 3.0 ports on the IO Shield).
   * 3.5 - All modems shall support 4G LTE (or lower) and have minimum bandwidth of 800 kbits/sec (under that Cerberus hits occur).
   * 3.6 - A RF USB 3.0 Type C dongle for mouse and keyboard control shall be permanently populated into the IO Shield and never removed.
     * DESIGN NOTE: This keeps the all the USB A 3.0 ports open for cameras which need to be connected to specific USB Host Controllers (See https://a.co/d/8kfb1GD)
   * 3.7 - There shall be the ability to connect a debugging HDMI monitor (connected through the GPU) to the OBC without removing any components.
     * DESIGN SPEC: This HDMI monitor shall NOT be permanently install in the vehicle and does NOT need a Display Port input.

4. Cables Harnesses:
   * 4.1 - All USB 2.0 cables for cameras shall be less then ?2.5 meters?, contain ground shielding, and have impedance controlled twisted pairs. 
   * 4.2 - All GPS antenna cables shall be less then ?1.5 meters? and coaxial cables with SMA connectors.
   * 4.3 - All cellular antenna cables shall be less then ?1.5 meters? and coaxial cables with SMA connectors.
   * 4.4 - All wires carrying analog voltage for control surfaces (e.g. brake & gas pedal) shall be less than 1 meter and multi-stranded.
     * 4.4.1 - All analog inputs into microcontrollers shall have local hardware based low pass filters.
       * Design Note: Cut off frequency determined based on real life Electromagnetic Interference (EMI) samples from a 6 GHz oscilloscope. 
   * 4.5 - All CAN Bus cables shall be less then 5 meters and ??? 
   * 4.6 Better labels on both ends of the cable 
   * 4.7 Vibratting and fretting 
   * 4.8 - Clean black caulking above the window for branding 
   * 4.9 Gromments to prevent body scrathes from car
   * 4.10 - No excessive length cable. 
   * 4.11 - Must be Commerical Off The Shelf (COTS) connectors

5. Security:
   * 5.1 - For legal / IP reasons is shall be clear that customers are not allowed to touch hardware.
   * 5.2 - The internal OBC box shall have "Do Not Taper" stickers.
     * DESIGN NOTE: [EXAMPLE STICKER THAT MAY CHANGE](https://www.grainger.com/product/38E801?gucid=N:N:PS:Paid:GGL:CSM-2295:4P7A1P:20501231&gclid=Cj0KCQiAutyfBhCMARIsAMgcRJR3yioMc0_DuhTHmW255EtnDVs2-LeNE-f4x5XzFgfv-0M7RsnVqO4aAo7JEALw_wcB&gclsrc=aw.ds)
   * 5.3 - The External Box (201-0001-A) shall have "Do Not Taper: Doing so means immediate removal from the Halo rental platform" text etched into metal.  
   * 5.4 - The Lid (201-0003-A) shall have two 4 digit pin EMBEDDED (Or dangling with rubber case and do not tamper tape with blank space to date time tape was applied) based locking systems.
   * 5.5 - REMOVED
   * 5.6 - The OBC Assembly (200-0001-A) shall contain NO source code, with as few binary executables as possible (goal is one).
   * 5.7 - The OBC login and SSH ports shall be protected by only passwords (not SSD encryption or a Data Loss Prevention (DLP) security strategy).    

6. Mechanical Structure:
   * 6.1 - The 4 holes drilled into the rear trunk floor for vibration dampers shall be defined by a stainless steel stencil.
   * 6.2 - The External Box (201-0001-A) and Lid (201-0003-A) shall be IP62 rated, while the Internal Box (201-0002-A) is not IP rated. 
     * DESIGN NOTE: IP6X means dust protected, but not dust tight.
     * DESIGN NOTE: IPX2 means protection against small low pressure indirect water drops, NOT submersion under water or water spray from a bottle or hose.
   * 6.3 - The taetr 
   YASH TO HELP

7. Production Cost:
   * 7.1 - The total "Part Database" cost per OBC shall be less than $ ??? grab data for Partsa Database
     * DESIGN NOTES: This doesn't include any cabling or cameras outside the OBC.
   * 7.2 - All OBC components shall have a lead time of less than 4 weeks.  
   * 7.3 - Halo Car shall stock at least 8 OBC's to buffer REQUIREMENT 7.2 (4 week lead time).
     * DESIGN NOTE: This assumes we can build 2 cars per week during initial production run (March 1, 2023 to Nov 1, 2023).


Mat machine shop local


### 2.2 Software V1 Functional Requirements:
1. Branding:
   *1.1 KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all software.


### 3.0 Dependency / Requirement Traceability Matrix:


### 4.0 Tracked Hardware / Software Issues:
1. See software bugs in LINEAR???
2. See hardware bugs at https://github.com/urbanrobo/OBC/issues

### 5.0 Project Management
See https://linear.app/halocar/team/HW/active

### 6.0 Free Form Scratch Pad for Hardware & Software V2 Requirements


### 7.0 GitHub Formatting  
See https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#lists
