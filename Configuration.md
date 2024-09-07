# Configurations
## Table of Contents

- [OS](#os)
- [Docker](#docker)
- [Pihole](#pihole)
- [Reverse Proxy](#reverse-proxy-ssl)
- [Firewall](#firewall)
- [Scanner](#scanner)


# OS
## Operating Systems 
As a quick overview of the OS's I used, I did a lot of research and found that Ubuntu had everything I needed and what I would be most familiar with. My Lab also includes Freebsd and Windows.

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

