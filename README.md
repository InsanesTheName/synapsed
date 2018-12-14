# synapsed

synapsed is a simple daemon written for Bash which invokes ews2case on a specified interval.

## Installation
Note: this guide assumes you have [Synapse](https://github.com/TheHive-Project/Synapse/) installed and configured as a systemd service. 
synapsed.service requires and binds to synapse.service.

Download synapsed and claim ownership:
```
sudo git clone https://github.com/InsanesTheName/synapsed /opt/synapsed
sudo chown -R synapse:synapse /opt/synapsed
```
Create the config directory, link to the config file, and set permissions:
```
sudo mkdir /etc/synapse
sudo chown -R synapse:synapse /etc/synapse
sudo ln -s /opt/synapsed/synapsed.conf /etc/synapsed/
sudo chmod 460 /etc/synapse/synapsed.conf
```
Create the log directory and set permissions:
```
sudo mkdir /var/log/synapse
sudo chown -R synapse:synapse /var/log/synapse
sudo chmod 2775 /var/log/synapse
```
Install the service and start it:
```
sudo systemctl enable /opt/synapsed/synapsed.service
sudo service synapsed start
```
