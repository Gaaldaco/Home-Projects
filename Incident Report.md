# Incident Report

Currently, there are no active incident reports due to the absence of a firewall and Wazuh not being operational. However, during the configuration of my reverse proxy, I was actively troubleshooting and monitoring logs in real-time. During this process, I observed a high volume of error responses indicating missing index pages and requests originating from an IP address that I did not recognize as being associated with my home network or known users of my URL.

Further investigation revealed that the IP address in question was from China. Although I cannot confirm the authenticity of this IP, I took precautionary measures by blocking the traffic associated with it on both my reverse proxy and router. Following this action, the suspicious requests ceased immediately, and no further traffic from that host was detected.

To enhance security moving forward, I plan to configure Wazuh to perform real-time monitoring of reverse proxy logs to identify and manage any high volumes of traffic more effectively.
