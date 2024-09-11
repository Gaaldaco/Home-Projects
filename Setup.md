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


# Portainer Integration into Home Lab

## Project Overview

This project focuses on integrating Portainer into a home lab environment to streamline container management and enhance visibility into Docker deployments. The goal was to simplify container orchestration, improve management efficiency, and provide an intuitive interface for monitoring and controlling Docker containers.

## Objectives

- **Container Management:** Facilitate easy management and orchestration of Docker containers.
- **User-Friendly Interface:** Provide a web-based GUI for managing containerized applications and services.
- **Monitoring and Logging:** Enhance visibility into container performance and logs.
- **Security and Access Control:** Implement role-based access control (RBAC) to manage permissions and ensure secure operations.

## Tools Used

- **Portainer:** A lightweight management UI for Docker environments, offering a simple and intuitive interface for container management.
- **Docker:** The containerization platform used for deploying and managing applications.
- **Docker Compose:** Used for defining and running multi-container Docker applications.

## Actions Taken

1. **Setup Portainer Environment:**
   - **Installed Portainer:** Deployed Portainer as a Docker container, setting it up on the same Docker host or a separate management server.
   - **Initial Configuration:** Configured Portainer with basic settings, including admin user accounts and connection settings for Docker.

2. **Container Management:**
   - **Connected Docker Environments:** Linked Portainer to existing Docker environments for centralized management.
   - **Created and Managed Containers:** Used Portainer’s UI to deploy, start, stop, and manage Docker containers.

3. **Monitoring and Logging:**
   - **View Container Metrics:** Monitored container performance metrics and resource usage through Portainer’s dashboard.
   - **Access Logs:** Utilized Portainer to view and analyze container logs for troubleshooting and performance tuning.

4. **Security and Access Control:**
   - **Configured User Roles:** Set up role-based access control (RBAC) to manage user permissions and ensure secure access to container management features.
   - **Secured Portainer Access:** Implemented SSL/TLS for secure communication with the Portainer interface.

5. **Continuous Improvement:**
   - **Updated Portainer:** Regularly updated Portainer to incorporate new features, security patches, and performance improvements.
   - **Refined Configuration:** Adjusted Portainer configurations based on user feedback and evolving management needs.

## Results

- **Streamlined Container Management:** Simplified the process of deploying, managing, and monitoring Docker containers with Portainer’s intuitive UI.
- **Enhanced Visibility:** Improved visibility into container performance and logs, facilitating easier troubleshooting and performance optimization.
- **Effective Security Controls:** Implemented robust role-based access controls and secured Portainer access to ensure safe and controlled container management.
- **Efficient Operations:** Increased operational efficiency with centralized management and automation features provided by Portainer.


Integrating Portainer into my home lab has significantly enhanced my ability to manage Docker containers, providing a user-friendly interface and comprehensive tools for monitoring and controlling containerized applications. This setup has streamlined container operations and improved overall management efficiency.

## Visual Overview
![Portainer](https://nextcloud.gahomeserver.duckdns.org/s/qiT77HtTnR8iLdA/preview)


# Jellyfin Integration into Home Lab

## Project Overview

This project involves integrating Jellyfin into a home lab environment to create a personal media server for streaming and managing a diverse collection of media content. Jellyfin is deployed behind a Caddy reverse proxy to provide secure and accessible media streaming.

## Objectives

- **Media Streaming:** Establish a server for streaming movies, TV shows, music, and other media to various devices.
- **Media Management:** Organize and manage a comprehensive media library with support for metadata and artwork.
- **User Access:** Implement user access controls and profiles for personalized media experiences.
- **Security and Accessibility:** Use Caddy as a reverse proxy to securely expose Jellyfin to the internet with automated SSL/TLS.

## Tools Used

- **Jellyfin:** Open-source media server software for streaming and managing personal media collections.
- **Docker:** Deployed Jellyfin in a containerized environment for ease of management and isolation.
- **Caddy:** Reverse proxy server used to handle SSL/TLS encryption and route traffic to Jellyfin.
- **Docker Compose:** Used to define and manage multi-container Docker applications, including Jellyfin and Caddy.

## Actions Taken

1. **Setup Jellyfin Environment:**
   - **Installed Jellyfin:** Deployed Jellyfin using Docker, configuring the container with necessary settings for media library paths and network configurations.
   - **Initial Configuration:** Set up Jellyfin’s basic settings, including media library locations and user accounts.

2. **Configure Caddy Reverse Proxy:**
   - **Installed Caddy:** Deployed Caddy using Docker, configuring it as a reverse proxy to handle incoming requests for Jellyfin.
   - **TLS Configuration:** Configured Caddy to automatically manage SSL/TLS certificates, ensuring secure access to the Jellyfin server.
   - **Proxy Rules:** Set up Caddy to route traffic to the Jellyfin container, handling domain and port routing.

3. **Media Library Management:**
   - **Added Media:** Imported and organized media files into Jellyfin, including movies, TV shows, and music.
   - **Metadata Configuration:** Set up metadata and artwork fetching to enhance the presentation of media content.

4. **User Access and Customization:**
   - **User Profiles:** Created user profiles and permissions for personalized media experiences and parental controls.
   - **Plugins and Customizations:** Installed and configured Jellyfin plugins to extend functionality and customize the user interface.

5. **Security and Monitoring:**
   - **Secure Access:** Ensured secure access to Jellyfin through Caddy’s automated SSL/TLS management.
   - **Performance Monitoring:** Monitored server performance and adjusted configurations for optimal media streaming quality.

6. **Continuous Improvement:**
   - **Update and Maintenance:** Regularly updated Jellyfin and Caddy to incorporate new features, security patches, and performance enhancements.
   - **Optimization:** Refined settings and configurations based on performance metrics and user feedback.

## Results

- **Reliable Media Streaming:** Successfully deployed a media server that streams a wide range of content to various devices.
- **Organized Media Library:** Effectively managed and organized a media library with rich metadata and artwork.
- **Secure and Accessible:** Ensured secure and reliable access to Jellyfin through Caddy’s automated SSL/TLS and reverse proxy capabilities.
- **Enhanced User Experience:** Provided a personalized media experience with user profiles and customizable settings.
- **Efficient Management:** Streamlined deployment and management with Docker and Docker Compose.


Integrating Jellyfin into my home lab with Caddy as the reverse proxy has created a powerful and secure media server solution. The setup offers efficient management, secure access, and a customizable platform for enjoying a vast media library, tailored to individual needs and preferences.

## Visual Overview

![Jellyfin Dashboard](https://nextcloud.gahomeserver.duckdns.org/s/bGgNJW2GtogJ2Gi/preview)

# Nextcloud Integration into Home Lab

## Project Overview

This project involves integrating Nextcloud into a home lab environment to create a self-hosted cloud storage solution. The goal was to set up a private cloud for file synchronization, sharing, and collaboration, with a focus on security and accessibility.

## Objectives

- **File Synchronization:** Establish a platform for syncing and accessing files across multiple devices.
- **File Sharing:** Enable secure file sharing and collaboration features for users.
- **User Management:** Implement user accounts and permissions to manage access and collaboration.
- **Security and Backup:** Ensure data security and regular backups to protect against data loss.

## Tools Used

- **Nextcloud:** Open-source cloud storage software for file synchronization, sharing, and collaboration.
- **Docker:** Deployed Nextcloud in a containerized environment for ease of management and isolation.
- **Database (e.g., MariaDB):** Used to manage Nextcloud’s data and metadata.
- **Reverse Proxy (e.g., Caddy or Nginx):** Configured to handle SSL/TLS termination and route traffic to the Nextcloud server.

## Actions Taken

1. **Setup Nextcloud Environment:**
   - **Installed Nextcloud:** Deployed Nextcloud using Docker, configuring it with necessary settings for file storage and network access.
   - **Database Configuration:** Set up a MariaDB container to manage Nextcloud’s database, ensuring proper integration with Nextcloud.

2. **Configure Reverse Proxy:**
   - **Installed Reverse Proxy:** Deployed and configured a reverse proxy (e.g., Caddy or Nginx) to handle external access to Nextcloud.
   - **TLS Configuration:** Enabled automated SSL/TLS management to secure communication between clients and Nextcloud.
   - **Proxy Rules:** Set up proxy rules to route traffic to the Nextcloud container, managing domain and port routing.

3. **User and File Management:**
   - **User Accounts:** Created user accounts and configured permissions for file access and collaboration.
   - **File Synchronization:** Set up synchronization clients on various devices to ensure seamless file access and updates.

4. **Security and Backup:**
   - **Security Measures:** Implemented security best practices, including strong authentication, encryption, and access controls.
   - **Backup Strategy:** Configured regular backups of Nextcloud data and database to prevent data loss.

5. **Continuous Improvement:**
   - **Update and Maintenance:** Regularly updated Nextcloud and related components to incorporate new features, security patches, and performance improvements.
   - **Performance Monitoring:** Monitored server performance and adjusted configurations to optimize Nextcloud’s functionality and user experience.

## Results

- **Efficient File Synchronization:** Successfully established a cloud platform for syncing and accessing files across multiple devices.
- **Secure File Sharing:** Enabled secure file sharing and collaboration with controlled user permissions.
- **Robust Security:** Ensured data security with SSL/TLS encryption and regular backups to safeguard against data loss.
- **User Management:** Provided comprehensive user management features for effective collaboration and access control.
- **Flexible Management:** Leveraged Docker and reverse proxy configurations for streamlined deployment and management.


Integrating Nextcloud into my home lab has provided a powerful, self-hosted cloud storage solution. This setup allows for efficient file synchronization, secure sharing, and effective collaboration, with robust security measures and flexible management features tailored to personal and organizational needs.

## Visual Overview

![NextCloud Dashboard](https://nextcloud.gahomeserver.duckdns.org/s/zysNyCJfnAPE9gz/preview)


# Collabora Integration into Home Lab

## Project Overview

This project involves integrating Collabora Online with Nextcloud in a home lab environment to provide a self-hosted office suite for online document editing and collaboration. The goal was to enhance Nextcloud with Collabora Online’s document editing capabilities, enabling seamless creation and modification of office documents directly from within the Nextcloud interface.

## Objectives

- **Document Editing:** Implement Collabora Online to enable online document editing directly within Nextcloud.
- **Real-Time Collaboration:** Facilitate real-time collaboration on documents with multiple users.
- **Seamless Integration:** Ensure smooth and effective integration between Collabora Online and Nextcloud.
- **Security and Access Control:** Implement secure access to document editing features and manage user permissions effectively.

## Tools Used

- **Collabora Online:** An open-source office suite that integrates with Nextcloud to provide online document editing and collaboration.
- **Nextcloud:** A self-hosted cloud storage platform providing file synchronization, sharing, and collaboration.
- **Docker:** Deployed Collabora Online in a containerized environment for ease of management and isolation.

## Actions Taken

1. **Setup Collabora Online Environment:**
   - **Installed Collabora Online:** Deployed Collabora Online using Docker, configuring it with the necessary settings for document editing and integration.
   - **Initial Configuration:** Set up Collabora Online with proper authentication and connection settings to ensure it works seamlessly with Nextcloud.

2. **Integrate with Nextcloud:**
   - **Nextcloud App Installation:** Installed and configured the Collabora Online app in Nextcloud to enable document editing features directly within the Nextcloud interface.
   - **Configuration:** Connected Nextcloud to the Collabora Online server, configuring the app settings to ensure smooth interaction and functionality.

3. **User and Security Management:**
   - **User Permissions:** Configured user permissions within Nextcloud to manage access to Collabora Online’s document editing features.
   - **Security Measures:** Implemented security best practices, including strong authentication methods and secure access controls to protect documents and user data.

4. **Continuous Improvement:**
   - **Update and Maintenance:** Regularly updated Collabora Online and Nextcloud to incorporate new features, security patches, and performance enhancements.
   - **Performance Monitoring:** Monitored system performance and made adjustments to optimize the document editing experience and overall server efficiency.

## Results

- **Enhanced Document Editing:** Successfully integrated Collabora Online with Nextcloud, providing powerful online document creation and editing capabilities.
- **Real-Time Collaboration:** Enabled real-time collaboration on documents, improving productivity and teamwork.
- **Seamless Integration:** Achieved a smooth and effective integration between Collabora Online and Nextcloud, offering a cohesive user experience.
- **Secure Document Access:** Ensured secure access to document editing features with effective user permissions and security practices.
- **Efficient Management:** Streamlined deployment and management with Docker, enhancing the overall efficiency of the setup.


Integrating Collabora Online with Nextcloud has significantly enhanced the document editing and collaboration capabilities within my home lab. This setup provides a robust and secure office suite that integrates seamlessly with Nextcloud, offering a powerful tool for managing and editing documents in a self-hosted cloud environment.


## Visual Overview

![Collabora](https://nextcloud.gahomeserver.duckdns.org/s/jm2HeRaN97bfJKt/preview)


