# Configurations
## Table of Contents

- [OS](#operating-systems-used)
- [Docker](#docker)
- [Pihole](#pihole)
- [Reverse Proxy](#reverse-proxy-ssl)
- [Firewall](#firewall)
- [Scanner](#scanner)




# Reverse Proxy/SSL
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
