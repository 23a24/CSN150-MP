# Cybersecurity 150 Midterm Project

## Name of Project
Setting Up Wireguard On Ubuntu (DigitalOcean)

## Purpose
To setup wireguard successfully onto a ubuntu server on digitalocean!

## Equipment
* [DigitalOcean (Using Ubuntu Droplet Server)](https://cloud.digitalocean.com/)

* [DigitalOcean's Server Console](https://cloud.digitalocean.com/)

## Link to Documentation Followed
- [DigitalOcean.com](https://www.digitalocean.com/community/tutorials/how-to-set-up-wireguard-on-ubuntu-22-04#creating-the-wireguard-peer-s-configuration-file)

##### Youtube Video 1: [Set Up Your Own Wireguard VPN Server on Ubuntu 22.04
- ZacsTech](https://youtu.be/FpbPeTuGNrM?si=Y0lWS6Nswe_YVN8Z) 

## Steps I followed
Installed wireguard using the package manager through the console of the ubuntu server droplet, managed to generate the appropriate cryptographic keys with wg genkey and wg pubkey, created /etc/wireguard/wg0.conf and added the right interface, private key, ip addresses, and listening port, edited /etc/sysctl.conf that enables both ipv4 + ipv6 forwarding, ran sudo sysctl -p to apply changes to system's ip forwarding configuration, used sudo systemctl start wg-quick@wg0 and sudo systemctl enable wg-quick@wg0 to start and wireguard service would run on start, confirmed wireguard was running by using sudo systemctl status wg-quick@wg0, ran ip a show wg0 to check the interface was up and configured properly, pinged the wireguard servers internal ip (10.8.0.1) to confirm successful connectivity, used sudo journalctl -u wg-quick@wg0 to monitor wireguard logs.

## Problems
Issues I've had were mostly related to losing my private key which lead me on a goose chase finding it, missing the wg0.conf file, package update confusion that lead to log errors and I had to reconfigure settings, readd command lines to the console so on... Basically triple check the directions while you FOLLOW THEM!!! Overall a lot of commands just to get wireguard installed onto a digitalocean ubuntu droplet working properly I cannot stress enough making sure you type things out CORRECTLY! It is a fun experience and I would do it again as I would definately have way less mistakes in the long run looking back at this.
