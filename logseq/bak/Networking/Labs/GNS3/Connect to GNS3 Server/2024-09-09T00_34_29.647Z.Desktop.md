# Configuring GNS3 Preferences and Web GUI

This documentation guides you through the process of configuring GNS3 preferences and using the GNS3 web GUI for managing your network simulations. These steps will help you set up GNS3 to work smoothly on your system.

## Step 1: Launch GNS3 and Access Preferences

1. Open the GNS3 application on your computer.

2. In the top-left corner of the GNS3 window, click on "Edit" and select "Preferences."

## Step 2: Configure Server Settings

1. In the "Preferences" window, navigate to the "Server" section, which is the second option from the top.

2. Set the following server settings:
   - **Host**: Enter the IP address of your GNS3 server.
   - **Port**: Set the port to `80`, **not** `3080`.

3. If you have set up authentication or a username and password for your GNS3 server, make sure to enable it by checking the "Enable" option.

4. Click "Apply" to save your server settings, then click "OK" to close the "Preferences" window.

## Step 3: Create or Open a GNS3 Project

1. After configuring the server settings, GNS3 will prompt you to either create a new project or open an existing one.

   - If you want to open an already created project, click on "Open Project" and select the desired project.

   - If you are creating a new project for the first time, click "Create a New Project" and provide a suitable name for your project. Click "OK" to create the project.

## Step 4: Access the Web GUI

1. To access the GNS3 web GUI, open a web browser and enter the following URL:

   ```
   http://your_gns3_server_ip
   ```

   Replace `your_gns3_server_ip` with the actual IP address of your GNS3 server.

2. Log in to the web GUI using your GNS3 server credentials if required.

## Step 5: Manage Your Network Simulations

1. With the GNS3 web GUI, you can perform most of your network simulation management tasks. It offers a smooth and intuitive interface for creating and configuring network topologies, devices, and connections.

2. Install Cisco images or other devices on the GNS3 server using the GNS3 application (GUI). Once you have uploaded the image to the server, it will be permanently available for use in your simulations.

3. Configure and manage your devices within the web interface. The web GUI provides extensive control over your network simulations.

By following these steps, you should have successfully configured GNS3 preferences, accessed the web GUI, and can now manage your network simulations efficiently, using both the GNS3 application and the web interface for a seamless experience.