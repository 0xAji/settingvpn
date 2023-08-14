# VPN
## Pre-Install
sudo apt update

## 1 install.sh
wget https://git.io/vpn -O openvpn-install.sh

sudo chmod +x openvpn-install.sh

./openvpn-install.sh
## 2 connect.sh

sudo apt update

sudo apt install apt-transport-https

sudo wget https://swupdate.openvpn.net/repos/openvpn-repo-pkg-key.pub

sudo apt-key add openvpn-repo-pkg-key.pub

sudo wget -O /etc/apt/sources.list.d/openvpn3.list https://swupdate.openvpn.net/community/openvpn3/repos/openvpn3-focal.list

sudo apt update

sudo apt install openvpn3

openvpn3 session-start --config cobasaja.ovpn

## 3 check ip

dig +short myip.opendns.com @resolver1.opendns.com
