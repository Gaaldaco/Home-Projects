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

For further details on configuration and management, refer to the [Ubuntu Server documentation](https://ubuntu.com/server/

# Home Lab Docker Setup

## Overview

This section covers the setup of various services in Docker containers and the use of Caddy as a reverse proxy on the host machine.

## Installation and Configuration

### 1. Docker Installation

1. **Install Docker**:
   - Follow the official [Docker installation guide](https://docs.docker.com/engine/install/) for your operating system to install Docker. 

2. **Install Docker Compose** (optional but recommended):
   - Docker Compose simplifies the management of multi-container applications. Install it by following the instructions [here](https://docs.docker.com/compose/install/).

### 2. Nessus in Docker

1. **Pull the Nessus Docker Image**:
   - Use the following command to pull the Nessus image from Docker Hub:
     ```bash
     docker pull tenableofficial/nessus
     ```

2. **Run Nessus Container**:
   - Start a Nessus container with the following command:
     ```bash
     docker run -d --name nessus -p 8834:8834 tenableofficial/nessus
     ```
   - Access Nessus via `http://<server_ip>:8834` to complete the setup.

### 3. Portainer

1. **Pull the Portainer Docker Image**:
   - Fetch the Portainer image:
     ```bash
     docker pull portainer/portainer-ce
     ```

2. **Run Portainer Container**:
   - Launch Portainer with:
     ```bash
     docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce
     ```
   - Access Portainer at `http://<server_ip>:9000` to manage Docker containers.

### 4. Nextcloud AIO in Docker

1. **Pull the Nextcloud AIO Docker Image**:
   - Retrieve the Nextcloud AIO image:
     ```bash
     docker pull nextcloud/all-in-one
     ```

2. **Run Nextcloud AIO Container**:
   - Start the Nextcloud AIO container:
     ```bash
     docker run -d -p 8080:80 --name nextcloud-aio --restart always nextcloud/all-in-one
     ```
   - Access Nextcloud via `http://<server_ip>:8080` and follow the on-screen instructions for setup.

### 6. Caddy on the Host Machine

1. **Install Caddy**:
   - Follow the installation instructions from the [Caddy website](https://caddyserver.com/docs/install) for your operating system.

2. **Configure Caddy**:
   - Create a `Caddyfile` with your desired configuration. Here’s a basic example:
     ```text
     example.com {
         reverse_proxy /nextcloud http://<server_ip>:8080
         reverse_proxy /pihole http://<server_ip>:80
     }
     ```
   - Place the `Caddyfile` in `/etc/caddy/Caddyfile` or the appropriate location based on your installation.

3. **Start Caddy**:
   - Start or restart Caddy to apply the configuration:
     ```bash
     sudo systemctl restart caddy
     ```

## Summary

This setup leverages Docker to run Nessus, Portainer, Nextcloud AIO, and Pi-hole, with Caddy serving as the reverse proxy on the host machine. This configuration ensures a modular, manageable, and accessible home lab environment.

For more detailed documentation on each service, refer to their respective official documentation:
- [Nessus](https://www.tenable.com/products/nessus)
- [Portainer](https://www.portainer.io/)
- [Nextcloud AIO](https://github.com/nextcloud/all-in-one)
- [Caddy](https://caddyserver.com/docs/)


