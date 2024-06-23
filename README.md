# Red Hat Enterprise Linux: Printer Installation Guide

![Red Hat Enterprise Linux](https://github.com/vladimak97/displaylink-rhel-9.4-workaround/assets/82274091/a98dbfbf-46ee-43f5-8603-349d1e2ba3fa)

This guide outlines the process I used to install and configure an HP printer (HP 5075) on my laptop running Red Hat Enterprise Linux 9.4 (Developer Edition). This setup allows you to connect and use the HP printer over a network.

Please note that this guide is based on my personal experience and may not be applicable to other versions or systems. However, it could be useful for others who are experiencing similar issues with this operating system.


## Disclaimer:

**This document provides instructions based solely on my personal experience setting up the HP 5075 printer on my laptop running Red Hat Enterprise Linux 9.4 (Developer Edition). Please be aware that this guide is not official and should not be considered professional advice. I take no responsibility for any outcomes resulting from the use of these instructions. Proceed at your own discretion.**


## Installation Steps

### 1. Install HPLIP

First, ensure that your system has HPLIP (HP Linux Imaging and Printing) installed. HPLIP includes the necessary tools and drivers to set up HP printers on Linux.

```bash
sudo yum install hplip
```

### 2. Run the HPLIP setup wizard

Run the HPLIP setup wizard to start configuring your printer.

```bash
hp-setup
```

### 3. Follow the Setup Wizard

Press y and then Enter to install the full feature driver and software.

```bash
Do you want to install the full feature driver and software? (y=yes*, n=no, q=quit) ? y
```

### 4. Search for Printers

The wizard will search for printers connected to your network. Ensure your printer is turned on and connected to the same network as your RHEL system.

```bash
Please wait. Searching for printers...
```

### 5. Found device

The wizard lists the printers it found on the network. Select the correct printer to proceed.

```bash
1. Found device: hp:/net/HP_5075_series?ip=XXX.XXX.X.XXX
```

### 6. Set Printer Queue Name

The queue name is how the printer will be identified on your system. You can accept the default or enter a custom name.

```bash
Using queue name: hp_5075_series
```

### 7. Enter Printer Description

Enter description for this printer: HP 5075 Printer

```bash
Enter description for this printer: HP 5075 Printer
```

### 8. Enter Printer Location

Specifying the location is optional but can be useful in an environment with multiple printers.

```bash
Enter location of the printer: Office Room
```

### 9. Name Your Printer

Naming your printer helps in easily identifying it on your network.

```bash
Enter a name for the printer (Enter 'q' to cancel): HP_5075_Printer
```

### 10. Print a Test Page:

Printing a test page ensures that the printer setup was successful and that it can communicate with your RHEL system.

```bash
Print a test page to verify your installation? (y=yes*, n=no, q=quit) ? y
```

## Acknowledgments
 
I would like to thank the developers of the following key components, without which this guide would not have been possible:

HPLIP (HP Linux Imaging and Printing): HPLIP provides the tools and drivers needed to set up and use HP printers on Linux.

I thank all the contributors to these project for their work and dedication in creating and maintaining these valuable resource.