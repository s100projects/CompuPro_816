# CompuPro 8/16 Restoration

![picture alt](Docs/CompuPro_8-16.jpg "CompuPro_816")

<b>Table of Contents:</b>
- [Project Purpose and Goal](#project-purpose-and-goal)
- [System Components](#system-components)
  - [CompuPro 816 Chassis](#compupro-816-chassis)
  - [CompuPro Connectors](#compupro-connectors)
  - [FDD HDD Emulation Drive Bay](#fdd-hdd-emulation-drive-bay)
  - [Wyse WY-60 CompuPro Connected Terminal](#wyse-wy-60-compupro-connected-terminal)
  - [TeleVideo 995-65 Terminal](#televideo-995-65-terminal)
- [MFM Emulation Files](#mfm-emulation-files)

# Project Purpose and Goal #
This particular CompuPro 8/16 S-100 Computer is a multi-user system that ran a central office business solution for a nation-wide high-end retail chain in the mid-80's to the mid 2000's.<br>  
The original base implementation was an order code of 816/F with a base price of $14,995 in 1984.<br>  <br>  <b>The features of this configuration included:</b>
- <b>CompuPro Enclosure 2:</b> 20-Slot S-100 Enclosure and Power Supply
- <b>CPU286</b> with Intel iAPX286 Processor
- 512K of Static Memory
- Dual 1.2M 8" Drives and Enclosure
- 40M-Byte Qume Hard Disk
- <b>Concurrent DOS 8/16</b>

The goal of this project is to restore the enclosure, system components, and acquire system terminals to bring the CompuPro system up with original software (Concurrent DOS 8/16) in a similar configuration to it's 1980's central office use.

<b>Current Status (February 2025):</b>

After a couple of years restoring the enclosure and motherboard (replacing a failed to reform power supply cap, and a few tantalums on S-100 boards), the CompuPro 8/16 was exhibited at VCF-Midewest in September 2024.  At that time, the initial setup of Concurrent DOS 8/16 Version 4.1E was complete, but not all software packages were configured properly for all terminals, nor were all system paramaters configured properly.  Still, the setup was reliable and drove one TeleVideo 995-65, one DEC VT-320 terminal, as well as two newer VGA based micro terminal emulators.

<b>Planned for VCF-Midwest 2025:</b>

With the recent addition of a "CompuPro Connected" Wyse WY-60 terminal, two additional Wyse terminals (WY-55's), an additional VT-320 terminal, and an additional TeleVideo (990) terminal, I will have the capability to show the full seven serial terminal setup of the CompuPro 8/16 as built in the 80's.  More information on the final demo details will be available as we get closer to the VCF-Midwest Show date in September 2025.

# System Components #
As originally used, the CompuPro 8/16 came with the following system components and boards (listed in order of slot placement):
- Enclosure 2:
  - 20-Slot Motherboard
  - 8V at 25-Amps
  - +/-16V at 3-Amps each
- 3 x SPUZ Slave Z-80 Processing Boards
  - 64K Local DRAM
  - 2 RS-232 Serial I/O Channels
- CPU286 Main Processor Board
- Alloy IDXCS-100T Tape Backup Interface Board
- 5 Static RAM Boards (768K Total)
  - 4 x RAM21 128K Static RAM Boards (512K)
  - 1 x RAM22 256K Static RAM Board
- System Support 1 Board
  - System Console Serial Port
  - Programmable Interval Timer
  - Real Time Clock with Battery Backup
  - 2 Priority Interrupt Controllers
  - PWRFAIL Signal Generation
- NET 100: ARCNET (DRNET) Network Interface Board
- PC Video (CGA and Keyboard) Interface (for PC-DOS Compatility)
- Interfacer 3+: 8-Channel RS-232 Serial Interface Board
- Interfacer 4:  3-Channel RS-232 Serial with 1 Centronics Parallel Port (added by current owner) 
- DISK 1A: 8" and 5-1/4" Floppy Disk Controller Board
- DISK 3: ST-506 Interface Hard Disk Controller Board

## CompuPro 816 Chassis ##

The CompuPro Chassis is a standard enclosure that hosted most of CompuPro's S-100 Packaged Systems;

![picture alt](Docs/CompuPro_Enclosure2.jpg "CompuPro Enclosure 2")

## CompuPro Connectors ##

Unlike modern PCs, the CompuPro has no internal floppy or hard drives, and networking (DRNET) was just getting started.  All connections (floppy and hard drives, serial terminals, printer outputs, video displays, and keyboard inputs) are positioned on the rear of the S-100 chassis:

![picture alt](Docs/Connector_Layout.jpg "CompuPro Layout")

As shown by the installed connectors, the orignal CompuPro system setup was configured for 7 users (6 serial terminals and 1 PC Video Display).  The System Console was only used during OS re-configurations, and so is normally not counted as a user terminal, but can be used as a MODEM port.

The total number of connecter interfaces available are:
- 1 x DB-25 RS-232 System Console Terminal 0 (also used for MODEMs)
- 6 x DB-25 RS-232 Ports (Terminals 1 to 6 or Users 4 to 9)
- 1 x DB-9 CGA Video Output (Color Video output for Users 1 to 3)*
- 1 x DIN-5 IBM-XT Keyboard Port (Keyboard input for Users 1 to 3)*
- 2 x DB-25 RS-232 Printer Ports (LPRT1 and LPRT2)
- 1 x 50-Pin Male Header (8" Floppy Disk Interface)
- 1 x 34-Pin Male Header (5-1/4" Floppy Disk Interface)
- 1 x 34-Pin Male Header (ST506 Hard Disk Interface)
- 2 x 20-Pin Male Header (Read/Write Channels for HDD1 and HDD2)
- 1 x BNC RF Connector for NET 100 (DRNET)

## FDD HDD Emulation Drive Bay ##

Although I have two of the orignal CompuPro external floppy drive bays, I do not have an original hard drive bay.  This makes it difficult to completely replicate a 1980s Qume Hard Drive setup.  Adding to that, since the 40MB and 80MB drives that the CompuPro 8/16 originally used are not now widely available and the fact that any 40 year old used drives would be of (very?) dubious reliability, I instead decided to use two Gotek Floppy Emulators and a <b>pdp8online</b> MFM Emulator for hard drive emulation.

![picture alt](Docs/MFM_EMU-Gotek_Drive_Bay.jpg "CompuPro Emulated Drive Bay")

I built this enclosure out of a used (and very abused!) Apple II drive enclosure that I had spare.  Since the rear panel of the enclosure was damaged, (and since Apple II drive bays are still very plentiful on eBay), I felt no qualms modifying this unit for the purpose.<br>
I also 3D-Printed a drive front panel and drive mounting cage that secures the Goteks and MFM Emulator in the original case mounting bosses.

<b>The advantages of this approach are:</b>
- More reliabiity (no moving parts)
- Smaller, low-weight package (much easier to carry to VCF!)
- Simplified backup of hard disk images (via WinSCP over ethernet)
- Easy to switch between hard disk and floppy image

## Wyse WY-60 CompuPro Connected Terminal ##

![picture alt](Docs/Wyse-60.jpg "Wyse WY-60 CompuPro Connected")

I acquired this terminal in Charleston (Thanks Terry!), and I was surprised to find it was a "CompuPro Connected" terminal.  I wasn't aware that such a relationship between CompuPro and Wyse existed into the 1990s.  It just shows that despite the rapid adoption of the IBM PC platforms, these mid-end business solutions were still a market presense throughout the 80s and 90s.

![picture alt](Docs/CPRO_Connected.jpg "Wyse WY-60 CompuPro Connected Label")

## TeleVideo 995-65 Terminal ##

![picture alt](Docs/TV_995-65.jpg "TeleVideo 995-65 User Terminal")

<b>The Heat Damaged Pizza Terminal</b>

This terminal was an eBay rescue from Texas.  It was an IT company lease to a national pizza chain call center based in the Dallas area, and was returned to the IT company (between Dallas and Houston) and stored outside under a tarp for a period of time.<br>

When I recieved the unit, it exhibited several signs of heat exposure and damage:
- A bowed bottom case (but no breaks, meaning the bow occured over time under heat)
- Leaking Caps
- Yellowed Case
- Unstable horizontal oscillator and switching power supply

<b>Replacing the Caps</b>

The first task was to replace the caps.  I chose to replace all the electrolytics due to the heat exposure.  This was also a preventative measure as this terminal was made during the "Capacitor Plague" and several of the caps were from affected cap manufacturers.  The Cap Replacement also fixed the Horizontal Oscillator and Switching Power Supply issues. <br>

The bowing at the bottom of the case was not fixed as the PCB (being hard mounted to the bottom of the case) also ended up with a bow, and I did not want to put stress on the PCB's solder joints. <br>

The case was Retro-Brited using the Hydrogen Perioxide Vapor Method (if interested in this method, search YouTube for it).

# MFM Emulation Files #

Following are two blank Hard Disk Emulation files for the CompuPro 8/16.  These are provided to allow other CompuPro users to start with a valid, low-level image that can then be formatted with the CompuPro hard disk format tools and CDOS Installation Disks.<br>

Two CompuPro compatible low-level images were generated, a <b>40MB Qume Q540</b> image, and an <b>80MB Control Data Corporation CD94155</b> image.  The drive specific formats are below.

<b>Qume Q540 Drive Specifics:</b>
  | <b>Drive Spec</b> | <b>Value</b> |
  |----------------|----------------|
  | <b>Cylinders</b>  | 512     |
  | <b>Heads</b>      | 8       | 
  | <b>Sectors/Track</b> | 17      |
  | <b>Formatted</b>  | 36MB |
  | <b>Unformatted</b> | 43MB |<br>  

<b>Control Data CD94155 Drive Specifics:</b>
  | <b>Drive Spec</b> | <b>Value</b> |
  |----------------|----------------|
  | <b>Cylinders</b>  | 925     |
  | <b>Heads</b>      | 9      | 
  | <b>Sectors/Track</b> | 17      |
  | <b>Formatted</b>  | 72MB |
  | <b>Unformatted</b> | 86MB |

The two disk images below were generated by the MFM Emulator using the following initialization commands:<br>

<b>Q540:</b><br>
`mfm_emu --drive 1 --file Q540 --initialize --cylinders 512 --heads 8`

<b>Control Data CD94155:</b><br>
`mfm_emu --drive 1 --file CDC80 --initialize --cylinders 925 --heads 9`

## Qume Q540 40MB Disk Image: ##

[Q540 40MB Disk Image](Docs/Q540.zip "Q540 40MB Low-Level Disk Image")

## Control Data CD94155 80MB Disk Image: ##

[CDC80 80MB Disk Image](Docs/CDC80.zip "CDC80 80MB Low-Level Disk Image")

