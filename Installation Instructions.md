# Installation Instructions

## Wazuh

Since I am using Wazuh for all local computers I decided to stick with the regular installation instead of setting up the reverse proxy.

Step 1. Make sure you linux system is completely up to date by using apt update & upgrade

    sudo apt update && apt upgrade

Step 2. Navigate to the Wazuh website and choose the way you'd like to install Wazuh. Here i will be showing you how I installed it on the host system using Ubunut Lixus
                
    https://documentation.wazuh.com/current/installation-guide/index.html

Step 3. Run all the commands below to install the Wazuh respitory and confirm connection to the respitory.

Download the Wazuh installation assistant and the configuration file.

    curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh
    curl -sO https://packages.wazuh.com/4.9/config.yml
    
Add the repository:
    
    echo "deb [signed-by=/usr/share/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list
    
Update the package information:

    apt-get update
