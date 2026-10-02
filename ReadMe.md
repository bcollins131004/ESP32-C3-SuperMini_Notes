# How to Flash ESP32-C3 Mini
### Step 1.
  Open *PowerShell*

### Step 2
  Run: 
  
  *pip install esptool*
  
  Then:
  
  *python -m esptool version*
  
  This confirms correct installation.

### Step 3
  Identify the com port your device is connected to.
    - Go to device manager
  <img width="416" height="95" alt="image" src="https://github.com/user-attachments/assets/8e0705ee-36c8-49c3-b5ea-87789563bb95" />

### Step 4
  Put the device into download mode:
  1. Hold **BOOT**
  2. Press and release **RESET**
  3. Release **BOOT**

### Step 5
  Run:
  *python -m esptool --chip esp32c3 --port COM5 erase_flash*
  
  Update COM5 with the connected com port.
  This Erases the old flash

### Step 6
  Navigate to the folder containing the firmware (Attached in GitHub page)
  eg:
  *cd downloads*

### Step 7
  
  Run:
  *python -m esptool --chip esp32c3 --port COM5 --baud 460800 write_flash -z 0 ESP32_GENERIC_C3-20260824-v1.29.0.bin*
  
  This updates the device with the file.

### Step 8
  Press reset button once to reset the device.


## Notes + backgorund

  I was encountering an issue with Thonny where I could not connect to the ESP32 and I was unable to update or install the firmware from Thonny, so I needed to do it from the Command prompt.

  After updating the device, Thonny should look like this:
  <img width="912" height="220" alt="image" src="https://github.com/user-attachments/assets/f6248543-3d8d-4865-bdda-dabf46344093" />
