# Installing Ubuntu Headless Server via Bootable USB

## Installation Steps

### 1. Prepare the Bootable USB Drive

1. **Download the Ubuntu Server ISO**:
   - Begin by downloading the latest Ubuntu Server ISO from the [Ubuntu Server download page](https://ubuntu.com/download/server).

2. **Create the Bootable USB Drive**:
   - On a Windows machine, use [Rufus](https://rufus.ie/) to create a bootable USB drive. Follow these steps:
     1. **Download and Install Rufus**:
        - Download Rufus and install it.
     2. **Insert the USB Drive**:
        - Plug in a USB drive with at least 4GB of capacity.
     3. **Open Rufus**:
        - Launch Rufus and select the USB drive from the device list.
     4. **Select the ISO File**:
        - Choose the downloaded Ubuntu Server ISO file by clicking the "Select" button next to the “Boot selection” dropdown.
     5. **Configure Partition Scheme**:
        - Opt for "GPT" for UEFI systems or "MBR" for BIOS systems, depending on the server’s configuration.
     6. **Start the Process**:
        - Click “Start” to create the bootable USB. Confirm any warnings about erasing data on the USB drive and wait for the process to complete.

### 2. Install Ubuntu Server

1. **Boot from USB Drive**:
   - Insert the bootable USB drive into the server. Power on the server and access the BIOS/UEFI settings (typically by pressing a key like F2, F12, DEL, or ESC during startup). Set the USB drive as the primary boot device, then save the changes and exit BIOS/UEFI. The server should boot from the USB drive.

2. **Start the Ubuntu Installer**:
   - The Ubuntu Server installer will start. Follow the on-screen prompts to select the preferred language and keyboard layout.

3. **Configure Network Settings**:
   - During the installation, configure the network settings. Ensure the server is connected to the network via Ethernet. Set up either a static IP address or use DHCP based on the network configuration.

4. **Set Up Storage**:
   - Choose the installation type (e.g., use the entire disk or manually set up partitions). Select the appropriate disk and confirm the partitioning scheme as needed.

5. **Create User and Password**:
   - Enter a username and password for the system. This user will have sudo privileges. Enable SSH access to facilitate remote management.

6. **Install Additional Software**:
   - When prompted, select additional software (e.g., OpenSSH server for remote access). Continue with the installation process as the installer copies files and sets up the system.

7. **Complete Installation**:
   - After installation, remove the USB drive and reboot the server. The server will boot into Ubuntu Server.

### 3. Post-Installation

1. **Access the Server Remotely**:
   - Find the server’s IP address by checking the router’s connected devices list. Use SSH from another machine to connect to the server:
     ```bash
     ssh username@server_ip
     ```
   - Replace `username` with the user account created and `server_ip` with the server’s IP address.

2. **Update and Upgrade**:
   - Once logged in, run the following commands to update the package list and upgrade installed packages:
     ```bash
     sudo apt update
     sudo apt upgrade
     ```

3. **Install Additional Software**:
   - Install any additional software or services needed:
     ```bash
     sudo apt install <package_name>
     ```

For further details on configuration and management, refer to the [Ubuntu Server documentation](https://ubuntu.com/server/docs).
