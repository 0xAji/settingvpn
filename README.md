# VPN
## Pre-Install
sudo apt update
sudo apt upgrade


## 1 install.sh
wget https://git.io/vpn -O openvpn-install.sh

sudo chmod +x openvpn-install.sh

./openvpn-install.sh
## 2 connect.sh


sudo mkdir -p /etc/apt/keyrings && curl -fsSL https://packages.openvpn.net/packages-repo.gpg | sudo tee /etc/apt/keyrings/openvpn.asc

echo "deb [signed-by=/etc/apt/keyrings/openvpn.asc] https://packages.openvpn.net/openvpn3/debian jammy main" | sudo tee /etc/apt/sources.list.d/openvpn-packages.list

sudo apt update && sudo apt upgrade -y

sudo apt install openvpn3

openvpn3 session-start --config cobasaja.ovpn

## 3 check ip

dig +short myip.opendns.com @resolver1.opendns.com
