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

##### Youtube Video 2: [How To Create Your Own WireGuard VPN Server Using An Ubuntu Linux VPS
- Websplaining](https://youtu.be/UFCSi2UMaiU?si=T94YtIiQXkX9ao0t)

## Steps I followed
Installed wireguard using the package manager through the console of the ubuntu server droplet, managed to generate the appropriate cryptographic keys with **wg genkey** and **wg pubkey**, created **/etc/wireguard/wg0.conf** and added the right interface, private key, ip addresses, and listening port, edited **/etc/sysctl.conf** that enables both ipv4 + ipv6 forwarding, ran **sudo sysctl -p** to apply changes to system's ip forwarding configuration, used **sudo systemctl start wg-quick@wg0** and **sudo systemctl enable wg-quick@wg0** to start and wireguard service would run on start, confirmed wireguard was running by using **sudo systemctl status wg-quick@wg0**, ran **ip a show wg0** to check the interface was up and configured properly, pinged the wireguard servers internal ip (10.8.0.1) to confirm successful connectivity, used **sudo journalctl -u wg-quick@wg0** to monitor wireguard logs.

## Problems
Issues I've encountered are as followed: losing my private key which lead me on a goose chase finding it, missing the **wg0.conf** file, package update confusion that lead to log errors and I had to reconfigure settings, and re-add command lines to the console to make everything work properly. Basically triple check directions!!! You can easily miss vital commands if you blink too fast. All of this just to get wireguard installed onto a digitalocean ubuntu droplet working properly. It is a fun experience and I would do it again as I would definitely have way less mistakes in the long run looking back at this. And for personal reasons, I could use this to create a secure VPN of my own which I find really useful which can route internet traffic through it and it's low-latency which is all good as I play multiplayer online games on my free time which would be very helpful against bad actors.
