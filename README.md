# Wireguard Docker Compose

This is completely based on [linuxserver/docker-wireguard](https://github.com/linuxserver/docker-wireguard).  
This is probably the simplest way to set up wireguard.  
Just go through the couple options that are present like your peers for example, start it up with `docker compose up -d` and start connecting your clients.  
You can always extend the peers list and restart the container to extend your generated peers.  

In case you don't like this approach you can also use [wg-easy](https://github.com/wg-easy/wg-easy).  

Also if you have some firewall like ufw you need to open up the wireguard port.

```
sudo ufw allow 51821/udp
```

Then you can either allow all traffic through your wireguard interface or restrict it for certain ports and/or peers.

Example for just the MySQL port:

```
sudo ufw allow in on wg0 to 10.13.13.1 port 3306 from 10.13.13.0/24
```

Example for all traffic:

```
sudo ufw allow in on wg0 from 10.13.13.1/24
```
