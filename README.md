# Washing Machine Controller - Digital Circuit

## Project Description
This project simulates a simple washing machine controller with both manual and automatic modes. The circuit is designed using Logisim and operates based on user-selected parameters or predefined washing programs.

### Functionality Overview
Initially, the washing machine is in an inactive state with the door open. The user can either manually set washing parameters (manual mode) or select one of the pre-programmed automatic modes.

#### Manual Mode
In manual mode, the user can configure:
- **Temperature:** 30°C, 40°C, 60°C, or 90°C
- **Spin Speed:** 800, 1000, or 1200 RPM
- **Additional Options:** Pre-wash and extra rinse

The washing duration depends on the selected temperature. Water starts at 15°C and heats up at a rate of 1°C every 2 seconds. Pre-wash and extra rinse options modify the washing duration accordingly.

#### Automatic Modes
The following automatic washing programs are available:
- **Quick Wash:** 30°C, 1200 RPM, no pre-wash, no extra rinse
- **Shirts:** 60°C, 800 RPM, no pre-wash, no extra rinse
- **Dark Colors:** 40°C, 1000 RPM, no pre-wash, extra rinse
- **Dirty Clothes:** 40°C, 1000 RPM, pre-wash, no extra rinse
- **Anti-Allergy:** 90°C, 1200 RPM, no pre-wash, extra rinse

### Washing Process Stages
Each washing program consists of the following steps:
1. **Main Wash:** Water fills the machine, heats up, rotates at 60 RPM for 20 minutes, then drains.
2. **Rinse:** Water fills, rotates at 120 RPM for 10 minutes, then drains.
3. **Spin:** Rotates at the selected speed for 10 minutes.
4. **Pre-Wash (if selected):** Follows the same process as the main wash but for 10 minutes.

Once a program starts, the door locks and unlocks one minute after the program finishes. The machine will not start with the door open.

### User Interface Controls
For better usability, we number the switches from left to right, 1 to 14:

- **Switch 1** - Start
- **Switch 2** - Reset
- **Switch 3** - Door
- **Switch 4** - Confirm
- **Switch 5** - Auto/Manual Mode
- **Switches 6-8** - Automatic Modes
- **Switches 9-10** - Temperature (Manual Mode)
- **Switches 11-12** - Speed (Manual Mode)
- **Switch 13** - Pre-Wash (Manual Mode)
- **Switch 14** - Extra Rinse (Manual Mode)

### LED Indicators
- **LED 1** - Machine On/Off Status
- **LED 2** - Door Locked/Unlocked Status

### Steps to Use the Washing Machine
1. Turn on the washing machine (**Start = 1**).
2. Close the door (**Door = 1**).
3. Select the desired washing mode:
   - **Manual Mode:** (**Auto/Manual = 1**) Then set:
     - Temperature:
       - 30°C - Both switches OFF
       - 40°C - First OFF, Second ON
       - 60°C - First ON, Second OFF
       - 90°C - Both switches ON
     - Speed:
       - 800 RPM - Both switches OFF
       - 1000 RPM - First OFF, Second ON
       - 1200 RPM - First ON, Second OFF
     - Pre-wash and extra rinse (optional)
   - **Automatic Mode:** (**Auto/Manual = 0**) Then set:
     - Quick Wash - All switches OFF
     - Shirts - Only last switch ON
     - Dark Colors - Only second switch ON
     - Dirty Clothes - Second and last switch ON
     - Anti-Allergy - Only first switch ON
4. Start the program (**Confirm = 1**).
5. Wait for the program to finish ("End" message on the display).
6. Turn off the washing machine (**Start = 0**).
7. Reset all switches.

---

![Circuit Diagram](https://github.com/CincaAlex/Washing-Machine-Controller-VHDL--Digital-Circuit/blob/main/img.png)  

---

