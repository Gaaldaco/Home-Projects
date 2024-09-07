# Installing Ubuntu Headless Server via Bootable USB

## Installation Steps

### 1. Prepare the Bootable USB Drive

1. **Download the Ubuntu Server ISO**:
   - Visit the [Ubuntu Server download page](https://ubuntu.com/download/server) and download the latest ISO file.

2. **Create the Bootable USB Drive**:
   - **On Windows**:
     1. Download and install [Rufus](https://rufus.ie/).
     2. Open Rufus and insert your USB drive.
     3. Select the Ubuntu Server ISO file in Rufus.
     4. Choose "GPT" or "MBR" partition scheme based on your system's UEFI/BIOS settings.
     5. Click "Start" and wait for the process to complete.

   - **On macOS**:
     1. Download and install [balenaEtcher](https://www.balena.io/etcher/).
     2. Open balenaEtcher and insert your USB drive.
     3. Select the Ubuntu Server ISO file in balenaEtcher.
     4. Click "Flash!" and wait for the process to complete.

   - **On Linux**:
     1. Insert the USB drive and identify its device name (e.g., `/dev/sdX`) using `lsblk` or `fdisk -l`.
     2. Use the `dd` command to write the ISO to the USB drive:
        ```bash
        sudo dd if=/path/to/ubuntu-server.iso of=/dev/sdX bs=4M status=progress
        ```
     3. Replace `/path/to/ubuntu-server.iso` with the path to your ISO file and `/dev/sdX` with your USB drive device name.

### 2. Install Ubuntu Server

1. **Boot from USB Drive**:
   - Insert the bootable USB drive into the server.
   - Power on the server and access the BIOS/UEFI settings (usually by pressing a key like F2, F12, DEL, or ESC during startup).
   - Set the USB drive as the primary boot device.
   - Save the changes and exit the BIOS/UEFI settings.

2. **Begin Installation**:
   - The server should boot from the USB drive and start the Ubuntu Server installer.
   - Follow the on-screen instructions to select language and keyboard layout.

3. **Configure Network**:
   - When prompted, configure network settings. Ensure your server is connected to the network via Ethernet or Wi-Fi.
   - You can set up a static IP or use DHCP based on your network configuration.

4. **Set Up Storage**:
   - Choose the installation type (e.g., use the entire disk or set up partitions manually).
   - Select the appropriate disk and partitioning scheme as needed.

5. **Set Up User and Password**:
   - Enter your desired username and password for the system. This user will have sudo privileges.
   - You may be prompted to set up SSH access; enable it to manage the server remotely.

6. **Install and Configure Additional Software**:
   - Choose additional software if needed (e.g., OpenSSH server to allow remote access).
   - Continue with the installation process. The installer will copy files and configure the system.

7. **Complete Installation**:
   - Once the installation is complete, you’ll be prompted to remove the USB drive and reboot the server.
   - The server will boot into Ubuntu Server.

### 3. Post-Installation

1. **Access the Server Remotely**:
   - Find the server’s IP address (check your router’s connected devices list if unsure).
   - Use SSH to connect to the server from another machine:
     ```bash
     ssh username@server_ip
     ```
   - Replace `username` with the user you created and `server_ip` with the server’s IP address.

2. **Update and Upgrade the System**:
   - Once logged in, update the package list and upgrade installed packages:
     ```bash
     sudo apt update
     sudo apt upgrade
     ```

3. **Install Additional Software**:
   - Install any additional software or services required for your setup:
     ```bash
     sudo apt install <package_name>
     ```

For detailed configuration and management, refer to the [Ubuntu Server documentation](https://ubuntu.com/server/docs).
