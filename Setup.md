# Configurations
## Table of Contents

- [OS](#os)
- [Caddy Reverse Proxy](#reverse-proxy-ssl)
- [Docker](#docker)
- [Nessus](#nessus)
- [TrueNas](#truenas-scale)
- [Wuzuh](#wazuh) currently in the works

# OS

## Overview

In my home lab, I use a variety of operating systems, each selected for its unique capabilities and suitability for specific roles.

## Operating Systems Used

### **Ubuntu Headless Server**

- **Purpose**: Hosts backend services and applications, providing a lightweight and efficient Linux environment.
- **Features**: Command-line interface for remote management, robust security, and support for a wide range of open-source tools.

### **Windows 11 Pro**

- **Purpose**: Functions as the main desktop environment for everyday tasks, development, and system administration.
- **Features**: User-friendly interface, advanced productivity features, and compatibility with numerous software applications.

### **FreeBSD**

- **Purpose**: Operates as a Network Attached Storage (NAS) solution, offering reliable and high-performance storage services.
- **Features**: Excellent stability, advanced file system capabilities, and strong network performance for managing and accessing stored data.

## Summary

These operating systems form the backbone of my home lab, each tailored to meet specific needs and enhance the overall functionality and efficiency of the setup.


# Reverse Proxy SSL
## Objective
Ensure secure communication between clients and the server by implementing SSL/TLS encryption.

## Tools Used
- Let’s Encrypt
- Caddy

## Actions Taken
- Installed Let’s Encrypt and configured auto-renewal of SSL certificates.
- Updated Caddy configuration to enforce HTTPS across all services.
- Implemented HTTP Strict Transport Security (HSTS).

## Results
- All traffic to Nextcloud and Jellyfin is securely encrypted.
- Achieved an A rating on SSL Labs for the domain.

## Screenshots
- ![SSL Labs Test Results](https://nextcloud.gahomeserver.duckdns.org/s/6rLx3KxCboooA4W/preview)
- ![Caddy Configuration](https://nextcloud.gahomeserver.duckdns.org/s/EPCfnS5mdx88Hsz/preview)


# Docker

## Objective

The goal of this home lab project is to create a flexible, efficient, and easily manageable environment for running various applications. Docker containers were chosen to streamline the deployment, management, and scaling of services including Nextcloud AIO, Portainer, Netdata, Nessus, and Pi-hole. By using Docker, the objective was to achieve:

- **Isolation**: To prevent conflicts and ensure independent operation of each application.
- **Portability**: To enable easy migration and consistency across different environments.
- **Resource Efficiency**: To optimize system resource usage and improve performance.
- **Simplified Management**: To facilitate easier updates, monitoring, and configuration.

## Tools Used

1. **Docker**: The core platform for containerization, providing isolation and management of applications.
2. **Docker Compose**: A tool for defining and running multi-container Docker applications.
3. **Portainer**: A web-based management interface for Docker, used for easy administration and monitoring of containers.
4. **Netdata**: Real-time performance monitoring tool for visualizing system metrics.
5. **Nessus**: Vulnerability scanning tool used for identifying security weaknesses.
6. **Pi-hole**: Network-wide ad blocker for blocking ads and trackers at the DNS level.
7. **Nextcloud AIO**: All-in-one solution for self-hosted file synchronization and sharing.

## Actions Taken

1. **Setup Docker Environment**:
   - Installed Docker and Docker Compose on the host machine.
   - Configured Docker to ensure proper isolation and resource management.

2. **Container Deployment**:
   - **Nextcloud AIO**: Deployed Nextcloud AIO using Docker to provide a comprehensive cloud storage solution. Configured persistent storage and networking.
   - **Portainer**: Set up Portainer for a user-friendly interface to manage and monitor Docker containers. Enabled container management and visual monitoring.
   - **Netdata**: Installed Netdata in a Docker container to monitor system performance metrics in real-time. Configured dashboards and alerts.
   - **Nessus**: Deployed Nessus within a Docker container for vulnerability scanning. Configured scanning profiles and scheduled scans.
   - **Pi-hole**: Set up Pi-hole in a Docker container to handle DNS queries and block ads across the network. Configured DNS settings and ad-blocking rules.

3. **Configuration and Management**:
   - Used Docker Compose to manage multi-container setups and ensure proper orchestration.
   - Configured networking and volume mappings to ensure data persistence and connectivity between containers.
   - Monitored container performance and health using Portainer and Netdata.

4. **Testing and Validation**:
   - Conducted testing to ensure all services were functioning correctly and securely.
   - Verified that Pi-hole was blocking ads, Nessus was performing scans, and Nextcloud AIO was providing cloud storage.
   - Reviewed and adjusted configurations based on performance and operational needs.

## Results

- **Enhanced Isolation**: Each application ran in its own container, preventing conflicts and ensuring stable operation.
- **Improved Portability**: Applications could be easily moved and redeployed across different environments with minimal adjustments.
- **Resource Efficiency**: Docker containers optimized resource usage, resulting in faster startup times and efficient utilization of system resources.
- **Streamlined Management**: Docker Compose and Portainer facilitated easy management and monitoring, reducing administrative overhead.
- **Effective Monitoring and Security**: Netdata provided real-time performance insights, while Nessus identified and addressed vulnerabilities. Pi-hole successfully blocked network-wide ads, improving browsing experience.
- **Consistent Operation**: Docker ensured consistent behavior of applications, regardless of underlying system changes.

Overall, using Docker containers in my home lab has significantly improved the efficiency, flexibility, and manageability of my applications, creating a robust and well-organized environment for both personal use and experimentation.

## Visual Overview
![Home Lab Diagram](https://nextcloud.gahomeserver.duckdns.org/s/oEaTJb5GPPnKmNs/preview)

# Nessus

## Objective

The objective of integrating Nessus into my home lab environment is to enhance network security through comprehensive vulnerability assessment and management. Nessus is used to identify potential security weaknesses, ensuring that all systems and applications are secure from known vulnerabilities. By implementing Nessus, the goals were to achieve:

- **Vulnerability Detection**: To identify and assess vulnerabilities in the network and system configurations.
- **Risk Management**: To prioritize and address vulnerabilities based on their potential impact and exploitability.
- **Compliance**: To ensure that systems meet security compliance standards and best practices.
- **Continuous Monitoring**: To regularly scan and update vulnerability information, maintaining a proactive security posture.

## Tools Used

1. **Nessus**: A widely-used vulnerability scanner that helps identify and assess vulnerabilities across networked systems.
2. **Docker**: Utilized to deploy Nessus in a containerized environment for ease of management and isolation.
3. **Nessus Plugins**: Plugins are used within Nessus to detect specific vulnerabilities and configuration issues.

## Actions Taken

1. **Setup Nessus Environment**:
   - **Deployed Nessus**: Installed Nessus in a Docker container to provide an isolated and manageable environment. Configured necessary networking settings to ensure connectivity.
   - **Initial Configuration**: Set up Nessus with basic configurations, including user accounts and license activation.

2. **Scan Configuration**:
   - **Created Scan Policies**: Defined and customized scan policies based on the types of vulnerabilities to be assessed (e.g., network, web applications).
   - **Scheduled Scans**: Configured scheduled scans to run periodically and continuously monitor network security.

3. **Vulnerability Assessment**:
   - **Performed Scans**: Executed vulnerability scans on various systems and network segments to identify security weaknesses.
   - **Analyzed Results**: Reviewed scan results to understand the vulnerabilities found, their severity, and potential impact.

4. **Reporting and Remediation**:
   - **Generated Reports**: Created detailed reports summarizing scan results, including vulnerabilities detected, risk levels, and recommendations for remediation.
   - **Addressed Findings**: Prioritized and addressed identified vulnerabilities based on their severity and potential impact on the network.

5. **Continuous Improvement**:
   - **Updated Plugins**: Regularly updated Nessus plugins to ensure the scanner can detect the latest vulnerabilities.
   - **Reviewed and Adjusted Scans**: Adjusted scan configurations and policies based on new findings and evolving security needs.

## Results

- **Effective Vulnerability Detection**: Nessus successfully identified vulnerabilities across various systems, providing detailed insights into potential security weaknesses.
- **Risk Management**: Enabled prioritization of vulnerabilities based on their risk levels, allowing for focused remediation efforts.
- **Compliance Achievement**: Assisted in meeting security compliance requirements by regularly scanning and addressing vulnerabilities.
- **Enhanced Security Posture**: Improved overall network security by proactively identifying and mitigating vulnerabilities.
- **Streamlined Management**: Docker containerization simplified the deployment and management of Nessus, while regular updates and adjustments kept the system current and effective.

Overall, integrating Nessus into my home lab has significantly strengthened my security practices by providing thorough vulnerability assessments and enabling proactive risk management.

## Visual Overview

![Nessus Dashboard](https://nextcloud.gahomeserver.duckdns.org/s/mjD4wo25KojXj9S/preview)


# TrueNAS SCALE

## Project Overview

This project involves integrating TrueNAS SCALE into a home lab environment to establish a robust, scalable, and highly available storage solution. The implementation aimed to enhance data management, ensure data protection, and streamline storage operations.

## Objectives

- **Scalable Storage:** Deploy a storage solution that accommodates increasing data needs with flexibility.
- **Data Protection:** Implement redundancy and snapshot capabilities to safeguard data.
- **High Availability:** Configure high availability to minimize downtime and ensure continuous data access.
- **Efficient Management:** Utilize an intuitive interface and automation features for streamlined storage management.

## Tools Used

- **TrueNAS SCALE:** Open-source, Linux-based storage operating system designed for scalability and high availability.
- **Docker:** For containerizing applications and services, enhancing deployment flexibility.
- **ZFS:** Advanced filesystem providing data integrity checks, compression, and snapshot features.

## Actions Taken

1. **Setup TrueNAS SCALE Environment:**
   - **Installation:** Deployed TrueNAS SCALE on dedicated hardware or a virtual machine. Configured initial settings and storage pools.
   - **Networking:** Set up networking configurations to ensure connectivity and access.

2. **Storage Configuration:**
   - **Storage Pools:** Created storage pools using ZFS for redundancy and performance.
   - **RAID Configuration:** Implemented RAID setups to enhance data protection and fault tolerance.
   - **Snapshots:** Enabled snapshot capabilities for effective data protection and recovery.

3. **Service and Application Management:**
   - **Docker Containers:** Deployed and managed Docker containers for additional services and applications.
   - **Network Shares:** Configured network shares (e.g., SMB, NFS) to facilitate data access from various systems.

4. **Data Protection and Backup:**
   - **Backup Solutions:** Implemented and configured backup strategies using TrueNAS SCALE’s built-in features or external tools.
   - **Scheduled Backups:** Established regular backup schedules to protect against data loss.

5. **Monitoring and Maintenance:**
   - **System Health:** Monitored system performance and health using TrueNAS SCALE’s monitoring tools.
   - **Updates:** Regularly updated TrueNAS SCALE to incorporate new features and security patches.

## Results

- **Scalable Storage Solution:** Successfully deployed a storage system capable of scaling with growing data needs and handling high workloads.
- **Enhanced Data Protection:** Achieved robust data protection with RAID configurations, snapshots, and regular backups.
- **High Availability:** Ensured high availability of critical data with minimal downtime and continuous access.
- **Efficient Management:** Streamlined storage management through TrueNAS SCALE’s user-friendly interface and automation features.
- **Flexibility and Integration:** Leveraged Docker for deploying and managing applications, enhancing overall functionality.



Integrating TrueNAS SCALE into my home lab has significantly improved my data management capabilities, providing a reliable, scalable, and efficient storage solution that supports both current and future requirements.

## Visual Overview

![TrueNas Dashboard](https://nextcloud.gahomeserver.duckdns.org/s/XgZ7YoCGE6Tntzf/preview)



