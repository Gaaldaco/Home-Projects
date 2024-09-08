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

### Vulnerability Assessments

- [Assessment Report 1](https://nextcloud.gahomeserver.duckdns.org/s/Ce7pmGwrXFMb7Lf/download/Home%20Lab_fwelwo.pdf)
- [Assessment Report 2](https://nextcloud.gahomeserver.duckdns.org/s/B8xeHA28E6KLrsD/download/Weekly%20scan_jdxv25.pdf)
  
Upon reviewing the assessments, it was determined that the Windows machine requires the most attention. Notably, it has several open ports and issues with ICMP that need to be addressed. The other machines in the network have SSL certificate vulnerabilities. Although I am not entirely certain how to resolve these issues at this time, it is worth noting that my reverse proxy is configured to use my CA from Let’s Encrypt, resulting in the primary certificate being used for website navigation.

Currently, all websites utilize self-signed certificates, but the vulnerability persists. It appears that a proper Certificate Authority (CA) may be necessary to fully address these issues. Despite these challenges, the remaining medium- and low-level vulnerabilities are managed, and overall, my home lab is secure and up to date.

side note my Windows machine changed IP as I updated the ethernet port to 2.5gbe and did not have a static IP set for the new card. Old IP (10.0.0.2) New IP (10.0.0.212)
### Incident Responses

- [Incident Report 1](link-to-report)
- [Incident Report 2](link-to-report)

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

