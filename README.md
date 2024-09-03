# SSL/TLS Configuration
## Objective
Ensure secure communication between clients and the server by implementing SSL/TLS encryption.

## Tools Used
- Let’s Encrypt
- Nginx

## Actions Taken
- Installed Let’s Encrypt and configured auto-renewal of SSL certificates.
- Updated Nginx configuration to enforce HTTPS across all services.
- Implemented HTTP Strict Transport Security (HSTS).

## Results
- All traffic to Nextcloud and Jellyfin is securely encrypted.
- Achieved an A+ rating on SSL Labs for the domain.

## Screenshots
- ![SSL Labs Test Results](https://nextcloud.gahomeserver.duckdns.org/s/S9cfNCBKdfcdag3/preview)
- ![Nginx Configuration](https://nextcloud.gahomeserver.duckdns.org/s/EPCfnS5mdx88Hsz/preview)
