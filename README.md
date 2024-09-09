# Welcome to My Homelab Project

## About Me

Hi, I'm Gene, and this is my homelab project. I'm showcasing this project to highlight my skills within cyber security.

![Profile Picture](https://nextcloud.gahomeserver.duckdns.org/s/CFB7jxzNkzrafEq/preview) <!-- Replace with your image -->

## Project Overview

In this project, I have set up a homelab environment that includes:
- **Nessus**: A Vulnerability Scanner
- **Nextcloud**: A self-hosted file sync and sharing service.
- **Jellyfin**: A media server for organizing and streaming media.
- **Collabora Online**: An online office suite.
- **Caddy**: A Reverse Proxy
- **Portainer**: Docker Container GUI
- **TrueNAS**: NAS

![Homelab Diagram](https://nextcloud.gahomeserver.duckdns.org/s/n8LGHRNM9E7roRk/preview) <!-- Replace with your diagram -->


## Security Analysis Focus

Here, I discuss how this project relates to security analysis. This includes:

- Security measures implemented
- Challenges faced and how they were addressed

## Portfolio of Work

## Vulnerability Assessments

- [Assessment Report 1](https://nextcloud.gahomeserver.duckdns.org/s/Ce7pmGwrXFMb7Lf/download/Home%20Lab_fwelwo.pdf)
- [Assessment Report 2](https://nextcloud.gahomeserver.duckdns.org/s/B8xeHA28E6KLrsD/download/Weekly%20scan_jdxv25.pdf)
  
Upon reviewing the assessments, it was determined that the Windows machine requires the most attention. Notably, it has several open ports and issues with ICMP that need to be addressed. The other machines in the network have SSL certificate vulnerabilities. Although I am not entirely certain how to resolve these issues at this time, it is worth noting that my reverse proxy is configured to use my CA from Let’s Encrypt, resulting in the primary certificate being used for website navigation.

Currently, all websites utilize self-signed certificates, but the vulnerability persists. It appears that a proper Certificate Authority (CA) may be necessary to fully address these issues. Despite these challenges, the remaining medium- and low-level vulnerabilities are managed, and overall, my home lab is secure and up to date.

side note my Windows machine changed IP as I updated the ethernet port to 2.5gbe and did not have a static IP set for the new card. Old IP (10.0.0.2) New IP (10.0.0.212)

## Incident Responses

Currently, there are no active incident reports due to the absence of a firewall and Wazuh not being operational. However, during the configuration of my reverse proxy, I was actively troubleshooting and monitoring logs in real-time. During this process, I observed a high volume of error responses indicating missing index pages and requests originating from an IP address that I did not recognize as being associated with my home network or known users of my URL.

Further investigation revealed that the IP address in question was from China. Although I cannot confirm the authenticity of this IP, I took precautionary measures by blocking the traffic associated with it on both my reverse proxy and router. Following this action, the suspicious requests ceased immediately, and no further traffic from that host was detected.

To enhance security moving forward, I plan to configure Wazuh to perform real-time monitoring of reverse proxy logs to identify and manage any high volumes of traffic more effectively.

## Technical Documentation

Detailed documentation on the setup, configuration, and maintenance of my homelab:

- [Setup Guide](https://github.com/Gaaldaco/Home-Projects/blob/main/Setup.md)
- [Configuration Files](link-to-files)
- [Installation Instructions](https://github.com/Gaaldaco/Home-Projects/blob/main/Installation%20Instructions.md#installing-ubuntu-headless-server-via-bootable-usb)

## Contact Information

Feel free to reach out to me:

- LinkedIn: [LinkedIn Profile](https://www.linkedin.com/in/gene-aldaco-47b493191/)
- Email: [aldacogene@gmail.com](mailto:aldacogene@gmail.com)

## Acknowledgements

Thank you to all the resources and individuals who have contributed to this project.

