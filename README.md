# 999-00003-A: OBC Requirements Document

Halo Car Inc uses a modified [US government design review process](https://en.wikipedia.org/wiki/Design_review_(U.S._government)) to design, fabricate, and distribute the  Kia Niro (KN) Series of cars.  This will aid in keeping the product within budget, on time, and limit requirement creep. All tasks and timelines will be tracked using [Linear](https://linear.app/halocar), Fusion 360 3D CAD models [Cloud Team Server](https://halo5.autodesk360.com/g/all_projects/active), business data stored in an organized [Halo_ALL](https://drive.google.com/drive/u/0/folders/0AKq4yLznZ1RzUk9PVA) Google Drive folder, and ALL other engineering data stored in multiple [Halo Hardware Github](https://github.com/orgs/urbanrobo/teams/hardware/repositories) repos.

**Future cars like Chevy Bolt and Tesla Model 3 shall only follow these requirements, if specifically called out in this document.**

AUTHOR(S): BLAZE SANDERS

APPROVED BY: ANAND NANDAKUMAR ON 2023-03-??-1300


## 1.0 Mission Concept Review (MCR)
See [Halo Pitch Deck](???) and [999-00001-A Kira Niro System Architecture Requirements Document](https://docs.google.com/document/d/1RNme7q0ufrCDHNyr7VOxuHKhVUad4LDPr4K3CM-rN78/edit) 

Objectives:
1. Allow any EV with ISO 11898-2 high-speed CAN Bus interface (1 Mbit/s on CAN, 5 Mbit/s on CAN-FD) to be remote piloted via 5G cellular.
2. Create rental fleet of 10 vehicles by April 15 that can be resold to dealerships for < $2k in repairs
3. ???                                                                                                                                           

Concepts to meet Objectives:
1. Analog man in the middle attack and digital CAN Bus reverse engineering. 
2. All additions must limit holes put into vehicle and not damage paint in all way.
3. ??? 

## 2.0 Mission Definition Review (MDR
All hardware and software requirements must be described in metric units (kg & cm)
2.1 Hardware V1 Functional Requirements:
Branding:
KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all hardware PCB’s and vehicle vinyl wraps.
Printed Circuit Boards
PCB Altium Project Template 
https://github.com/jose-halocar/ee_altium_template/blob/master/HaloCar_Project_Rename_This_File.PrjPcb
Schematics:
PCB Layouts:
Series PCB  shall be conformal coated 
https://zymet.com/p-reworkable-edgebond-adhesives.html
www.masterbond.com/certifications/nasa-low-outgassing
www.masterbond.com/tds/ep21tcht-1 or www.masterbond.com/tds/ep30lte-lo-black
CPU Subsytem:
KN Series shall use the ST ARM G4 family of microcontrollers.
Cables Harnesses:
KN Series analog inputs shall have some low pass filter on all ADC inputs. 
Design Note: Cut off frequency could be calculated based on sampled signal frequency
Four layer stackup as defined in the following Altium template: https://github.com/jose-halocar/ee_altium_template/tree/master/outjobs
2.2 Software V1 Functional Requirements:
Branding:
KN Series shall use Blue (0x2342F5), Yellow (0xF7C664), and/or White (0xFFFFFF) branding colors on all software.


3.0 Dependency / Requirement Traceability Matrix:


4.0 Tracked Hardware / Software Issues:

See software bugs in LINEAR???
See hardware bugs at https://github.com/urbanrobo/DriveByWirePCB/issues
5.0 Project Management
See https://linear.app/halocar/team/HW/active
6.0 Free Form Hardware & Software V2 Requirements
