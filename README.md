## Specification
* Dell Wyse Dx0d (2GB RAM, 8GB ROM)
* Debian 11 Bullseye

## Bootstrap
```shell
sudo su -c "bash <(wget -qO- to-update)" root
```

## What's included?
### Install script
* Turn off MOTD
* [Debloat APT](https://dennislee.xyz/2020/debian-eliminate-dependency-bloat/)
* Enable contrib and non-free APT repositories
* Install Software
  * Docker
  * Openssh server
  * Vim
  * firmware-linux-nonfree 
  * amd-microcode
### Docker Services
* [No-ip](https://github.com/maciej-umanski/docker-no-ip)
* [Pi-hole](https://github.com/pi-hole/docker-pi-hole) + [Unbound](https://github.com/MatthewVance/unbound-docker-rpi)
* [OpenVPN](https://github.com/dockovpn/dockovpn)
* [Samba](https://github.com/dperson/samba)

## Misc
### OpenVPN
* Forward UDP port 1194 to your box
* Retrieve client configuration: 
```shell
docker exec openvpn wget -q --output-document - localhost:8080 | tee client.ovpn > /dev/null
```