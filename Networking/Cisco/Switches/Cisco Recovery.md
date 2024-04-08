
## Recovering a Cisco Device with ROMMON Mode

### Introduction:

ROM Monitor (ROMMON) mode is a crucial tool for recovering a Cisco device when the regular IOS (Internetwork Operating System) is not functioning correctly or when you need to restore a device to its working state. This guide outlines the steps to access ROMMON mode and recover your device.

### Prerequisites:

Before proceeding, ensure you have the following:

- Physical access to the Cisco device.
- A console cable to connect your computer to the device.
- A terminal emulator program (e.g., PuTTY, Tera Term, or HyperTerminal) installed on your computer.
- A TFTP (Trivial File Transfer Protocol) server with the correct firmware image you want to load onto the device.

### Accessing ROMMON Mode:

1. **Interrupt the Boot Sequence**:
   - While the device is booting up, quickly press `Ctrl + Break` on your keyboard (or `Ctrl + Pause/Break` on some keyboards) when you see the boot messages. This action interrupts the normal boot process and allows access to ROMMON mode.
   - Note: Be prompt in executing this step to prevent the IOS image from decompressing; if it starts, you'll need to reboot the device.

### Configuring Network and Variables:

2. **Set IP and Network Variables**:
   - In the ROMMON mode prompt (e.g., `rommon 1>`), set the following network-related variables with the values appropriate for your network configuration:
     - `IP_ADDRESS`: The IP address for the Cisco device.
     - `IP_SUBNET_MASK`: The subnet mask for the Cisco device.
     - `DEFAULT_GATEWAY`: The default gateway for the Cisco device.
     - `TFTP_SERVER`: The IP address of the TFTP server where your new firmware image is stored.

   Example:
   ```
   rommon 1> IP_ADDRESS=172.16.200.200
   rommon 2> IP_SUBNET_MASK=255.255.0.0
   rommon 3> DEFAULT_GATEWAY=172.16.1.1
   rommon 4> TFTP_SERVER=172.16.1.13
   ```

3. **Specify Firmware Image**:
   - Set the `TFTP_FILE` variable to specify the filename of the new firmware image you want to download from the TFTP server.

   Example:
   ```
   rommon 5> TFTP_FILE=c2600-c-mz.123-1.bin
   ```

### Downloading and Booting the New Image:

4. **Download the New Image**:
   - Use the `tftpdnld` command to download the new firmware image from the TFTP server. This command initiates the download process.
   
   Example:
   ```
   rommon 6> tftpdnld
   ```

5. **Confirm and Reboot**:
   - After the download is complete and successful, confirm the new image's presence on the device using the `dir` command.
   - Set the `BOOT` variable to specify which image the device should use for the next boot.
   - Finally, use the `reset` command to reboot the device with the new image.

   Example:
   ```
   rommon 7> BOOT=flash:c2600-c-mz.123-1.bin
   rommon 8> reset
   ```

### Conclusion:

You have successfully recovered your Cisco device using ROMMON mode. Ensure that you have the correct firmware image and follow these steps carefully to prevent any disruptions to your device's operation.	ROMMON mode is a powerful tool for troubleshooting and recovery, and its usage should be approached with caution.