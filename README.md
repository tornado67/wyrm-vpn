# Wyrm RaspberryPI VPN router

## Installation


Currently this project works only with WireGuard VPN servers and Raspbian.

This setup expects you to have a DHCP server running on your local machine and leasing addresses to any device connected to the ethernet port  to which your RaspberryPI is connected.


Under `ansible/roles/wyrm/defaults/main.yml` set:

```
wireguard_server_endpoint
wireguard_client_ip
wireguard_client_private_key
wireguard_server_public_key
```
and make sure that interface names under 

```
eth0_interface
wlan0_interface
```
are correct and run `wyrm.yml` playbook making sure `inventory.ini` contains correct raspberry host:



```
ansible-playbook -i inventory.ini wyrm.yml
```
