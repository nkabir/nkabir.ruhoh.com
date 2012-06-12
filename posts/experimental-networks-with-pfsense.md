---
title: Experimental Networks with pfSense
date: '2012-06-03'
description: Testing networking configurations with private virtual networks
categories: sysadmin
tags: 
    - ubuntu
    - precise
    - blackbox
    - network
    - pfsense

layout: post

---

## Virtual Networks

In addition to providing an easy way to test operating systems, VirtualBox also provides a way to test networks.

<img src="{{urls.media}}/pfsense-virtual-network.png"/>

## Setup

### VirtualBox

Turn off VirtualBox's internal DHCP server (via Preferences).

1. Create a new guest on VirtualBox as a 64-bit FreeBSD instance. pfSense has modest resource requirements.
2. Assign 256Mb of RAM and 16GB of storage.
3. Create two network interfaces. Both must be PCnet II (`Am79C970A`)&mdash;FreeBSD has native driver support for this card.
4. Make one card internal (`intnet`) and the other should either be NAT or Bridged.

### Install pfSense

1. Download [pfSense](http://pfsense.org). I used the [Chicago mirror](http://files.chi.pfsense.org/mirror/downloads/).
2. Install using _Quick Install_.
3. Assign one interface `le0` to WAN and the second, `le1`, to LAN.
4. Point your browser (from a machine on the internal network) to https://{pfsenseipaddress}

The default username is `admin` and default password is `pfsense`.

You may want to change the subnet for your experimental network. I use `172.16.50.1` to avoid colliding with `192.168.x.x` and `10.x.x.x` networks that are more common.

You can accomplish this via the command-line interface on pfsense (selection `2 - Set interface(s) IP address`) or via the web interface.

<img src="{{urls.media}}/pfsense-172.png"/>

pfSense also includes a DHCP server by default. If you are testing DHCP services on your internal network, be sure to turn it off. It's listed under Services.

Finally, if you are running DHCP on your lan (host machine network), you may want to set up a DHCP lease reservation for the WAN interface to ensure you always get the same IP address for your experimental network.

### Set Static IP on Ubuntu

If you are going to run DHCP on your experimental network, you'll need to assign a static ip to your DHCP server. There are two options&mdash;you can install the `bbstaticip` package or your can edit the files below by hand.

Edit `/etc/network/interfaces`

	auto eth0
	iface eth0 inet static
	    address 192.168.1.100
	    netmask 255.255.255.0
	    network 192.168.1.0
	    broadcast 192.168.1.255
	    gateway 192.168.1.1
	    dns-nameservers 192.168.1.254
	    dns-search example.com example.me

Note that your values may differ. Then restart networking

	$ sudo /etc/init.d/networking restart

### Set Full Hostname on Ubuntu

Note that this is also accomplished by installing `bbstaticip`.

Edit `/etc/hosts` to provide your machine with a fully qualified domain name:

	127.0.0.1  apollo.example.com apollo localhost
	127.0.1.1  apollo.localdomain apollo

_Order matters._ Please see the [following post](/sysadmin/machine-names).

### Port Forwarding

You may want to access the machines on your experimental network via SSH. To enable this, you'll need to turn on port forwarding on pfSense. But before you do, make sure you uncheck _Block private networks_ and _Block bogon networks_ on your WAN interface settings. 

_NOTE: Only do this on your desktop configuration&mdash;never in production._

<img src="{{urls.media}}/pfsense-private-networks.png"/>

Then go to `Firewall->NAT` and create a new port forwarding rule (in this case, forward WAN port `2222` to `22` on an internal host).

<img src="{{urls.media}}/pfsense-port-forward.png"/>

One last piece of advice&mdash;always keep a root shell logged in when experimenting with authentication and networking.
