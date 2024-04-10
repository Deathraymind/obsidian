**Bug Documentation: Spice Server Contact Issue with Looking Glass on Windows 10/11**

---
#KVM 
**Description:**
When using Looking Glass with Windows 10 or 11, users may encounter a bug where the Spice server fails to establish proper contact if no physical monitor is connected to the system. This documentation provides steps to resolve this issue by installing a virtual display driver and configuring monitor options.

---

**Resolution Steps:**

1. **Download the Virtual Display Driver:**
   - Download the virtual display driver from [this repository](https://github.com/ge9/IddSampleDriver).
   - Alternatively, directly download the driver from [this link](https://github.com/ge9/IddSampleDriver/releases/tag/0.0.1.2).

2. **Driver Installation:**
   - Extract the downloaded driver archive to the root of the Windows system disk (typically `C:\`).
   - Navigate to the extracted folder (`C:\IddSampleDriver`).

3. **Create Configuration File:**
   - Within the `C:\IddSampleDriver` folder, create a new text file named `options.txt`.

4. **Configure Options:**
   - Open the `options.txt` file and add the following lines:

```plaintext
1
#lines beginning with "#" are ignored (comment)
#the first line must be a positive integer (small number (<5) is recommended)), NOT comment
#(currently) the location of this file must be "C:\IddSampleDriver\option.txt" (hard-coded)
#numbers should be separated by comma
#spaces before number are allowed
640,  480, 60
800,  600, 60
1024,  768, 60
1152,  864, 60
1280,  600, 60
1280,  720, 60
1280,  768, 60
1280,  800, 60
1280,  960, 60
1280, 1024, 60
1360,  768, 60
1366,  768, 60
1400, 1050, 60
1440,  900, 60
1600,  900, 60
1680, 1050, 60
1600, 1024, 60
1920, 1080, 60
1920, 1200, 60
1920, 1440, 60
2560, 1440, 60
2560, 1600, 60
2880, 1620, 60
2880, 1800, 60
3008, 1692, 60
3200, 1800, 60
3200, 2400, 60
3840, 2160, 60
3840, 2400, 60
4096, 2304, 60
4096, 2560, 60
5120, 2880, 60
6016, 3384, 60
7680, 4320, 60
```

This file should be created as `C:\IddSampleDriver\options.txt` with the provided content.

Then run this in CMD
```
cd C:\Program Files (x86)\Windows Kits\10\bin\10.0.22621.0\x64
CertMgr.exe /add C:\IddSampleDriver\IddSampleDriver.cer /s /r localMachine root
```
If that CertMgr.exe does not exist download the windows 10 sdk download page. 
https://developer.microsoft.com/en-us/windows/downloads/windows-sdk/
5. **Install the Virtual Display Driver:**
   - Open Device Manager.
   - Click on any device and then click on "Action" in the top panel.
   - Select "Add legacy hardware" from the dropdown.
   - Click "Next" and choose "Install hardware that I manually select from a list (Advanced)".
   - Proceed by clicking "Next" while ensuring "Show all devices" is selected.
   - Choose "Have disk" and then "Browse".
   - Locate and select the `C:\IddSampleDriver\IddSampleDriver.inf` file, then click "OK".
   - Continue with "Next" and then "Next" to complete the installation.

6. **Monitor Installation Confirmation (Windows 11):**
   - After successful installation, on Windows 11, an animation should indicate the monitor installation.

7. **Configuration:**
   - Once the driver is installed, configure your virtual monitor settings as desired by editing `C:\IddSampleDriver\option.txt`.

8. **Disconnect Physical Monitor:**
   - Once the virtual display driver is installed and configured, you can disconnect the physical monitor.

9. **Set Virtual Monitor Resolution:**
   - Use Looking Glass to set the resolution of the virtual display as needed.

10. **Set Mouse Settings:**
   - To fix the annoying mouse leaving the screen we have to disable mouse acceleration.
   - Navigate to Start > Settings > Devices > Mouse. Choose Additional mouse options > Pointer Options > and uncheck Enhance pointer precision. 
 
---

**Note:** Ensure to follow the steps carefully, and it's recommended to have administrative privileges while performing these actions. This documentation aims to address the issue of Spice server contact failure with Looking Glass on Windows 10 and 11 due to the absence of a physical monitor.