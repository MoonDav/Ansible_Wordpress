1. ������ ����: /etc/netplan/01-network-manager-all.yaml
	addresses: [ 192.168.0.33/24 ]

sudo netplan generate
sudo netplan apply

sudo ip a
sudo resolvectl status

2. ������ HostName: 
sudo hostnamectl set-hostname _Pingvinus_
sudo nano /etc/hosts
sudo nano /etc/hostname

��������:
hostnamectl

3. �������� MAC ������:
ifconfig -a | grep ether | gawk '{print $2}'
ip a | grep ether | gawk '{print $2}'

4. �������� machine-id
sudo rm /etc/machine-id
sudo systemd-machine-id-setup
cat /etc/machine-id


