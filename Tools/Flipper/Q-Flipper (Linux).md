# Documentation: Downloading and Running qFlipper 1.3.3 on Linux
#flipper
- ## Introduction
  This guide provides step-by-step instructions for downloading and running qFlipper version 1.3.3 on a Linux system. qFlipper is the official software used for updating the Flipper Zero device firmware. This guide assumes the use of automated keyboard commands for executing the process.
- ## Prerequisites
- A Linux-based operating system.
- Internet connectivity to download qFlipper.
- Sudo privileges for the executing user.
- ## Automated Download and Execution Process
- ### 1. Opening the Terminal
- Initiate the terminal using the keyboard shortcut `CTRL-ALT-T`.
- This step opens a new terminal window on most Linux distributions.
- ### 2. Navigating to the Downloads Directory
- After the terminal is open, navigate to the Downloads directory:
  ```bash
  cd Downloads
  ```
- The `DELAY 600` (milliseconds) ensures there's enough time for the terminal to open before the command executes.
- ### 3. Downloading qFlipper
- Use the `wget` command to download qFlipper 1.3.3 AppImage: stuff
  ```bash
  wget https://update.flipperzero.one/builds/qFlipper/1.3.3/qFlipper-x86_64-1.3.3.AppImage
  ```
- `DELAY 300` provides a brief pause to ensure the directory change command completes.
- ### 4. Running qFlipper
- After downloading, execute the AppImage:
  ```bash
  sudo ./qFlipper-x86_64-1.3.3.AppImage
  ```
- `DELAY 4000` gives time for the download to complete. Adjust this delay based on your internet speed.
- ### 5. Finalizing Setup
- The AppImage should launch qFlipper, and from here, you can connect your Flipper Zero device to update or manage its firmware.
- ## Considerations
- **Automated Delays**: Adjust the delays (`DELAY`) according to your system's response time and internet speed.
- **Running as Superuser**: The use of `sudo` might not be necessary for all systems to execute an AppImage. If your user has the required permissions, you can run the AppImage without `sudo`.
- **File Permissions**: Ensure the downloaded AppImage has execute permissions. Use `chmod +x qFlipper-x86_64-1.3.3.AppImage` if needed.
- ## Conclusion
  By following these automated steps, you can easily download and run qFlipper on your Linux system, facilitating the management of your Flipper Zero device. Remember to regularly check for updated versions of qFlipper to maintain compatibility and access new features.