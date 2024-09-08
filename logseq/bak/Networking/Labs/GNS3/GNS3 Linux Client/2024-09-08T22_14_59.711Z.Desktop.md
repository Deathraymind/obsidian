# Installing GNS3 on Linux

This documentation provides step-by-step instructions for installing GNS3, a network simulation software, on a Linux system. GNS3 allows you to create, configure, and test complex network topologies for learning and testing network configurations.

## Step 1: Add GNS3 Repository

1. Open a terminal on your Linux machine.

2. Add the GNS3 repository to your package manager's sources list using the following command:

   ```bash
   sudo add-apt-repository ppa:gns3/ppa
   ```

   This command adds the GNS3 repository to your system, allowing you to install GNS3 and its components.

## Step 2: Update Package Lists

1. To ensure your package manager has the latest information about available packages, update the package lists:

   ```bash
   sudo apt update
   ```

   This command fetches the latest package information from the added GNS3 repository.

## Step 3: Install GNS3 GUI

1. Install the GNS3 GUI by running the following command:

   ```bash
   sudo apt install gns3-gui
   ```

   This command installs the GNS3 graphical user interface (GUI) component on your system. It provides a user-friendly interface for creating and managing network topologies.

## Step 4: Add User to Required Groups

1. To enable various features and functionalities in GNS3, add your user to specific groups using the following command. Replace `$(whoami)` with your username:

   ```bash
   sudo usermod -aG ubridge,libvirt,kvm,wireshark $(whoami)
   ```

   - `ubridge`: Allows GNS3 to create virtual bridges for network connections.
   - `libvirt`: Provides support for virtualization features.
   - `kvm`: Enables kernel-based virtualization for improved performance.
   - `wireshark`: Grants access to packet capture capabilities.

   Adding your user to these groups ensures that GNS3 can interact with your system's network and virtualization components effectively.

## Step 5: Launch GNS3

1. After completing the installation and group assignments, you can launch GNS3 by searching for it in your system's applications menu or running the following command:

   ```bash
   gns3
   ```

or just use the normal linux launcher

2. Follow any on-screen instructions and setup prompts to configure GNS3 according to your preferences.

3. Once configured, you can start creating and simulating network topologies using the GNS3 GUI.

Congratulations! You have successfully installed GNS3 on your Linux system and can now use it for network simulation and learning purposes. Enjoy exploring its features and capabilities.