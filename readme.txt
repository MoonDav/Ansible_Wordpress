1. Меняем сеть: /etc/netplan/01-network-manager-all.yaml
	addresses: [ 192.168.0.33/24 ]

sudo netplan generate
sudo netplan apply

sudo ip a
sudo resolvectl status

2. Меняем HostName: 
sudo hostnamectl set-hostname _Pingvinus_
sudo nano /etc/hosts
sudo nano /etc/hostname

Проверка:
hostnamectl

3. Проверка MAC адреса:
ifconfig -a | grep ether | gawk '{print $2}'
ip a | grep ether | gawk '{print $2}'

4. Изменить machine-id
sudo rm /etc/machine-id
sudo systemd-machine-id-setup
cat /etc/machine-id


