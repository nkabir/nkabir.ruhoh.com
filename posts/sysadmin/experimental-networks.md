---
title: Experimental Networks
date: '2012-09-21'
description: Setting up a subnet
categories: sysadmin
tags:
    - ubuntu
    - precise
    - blackbox

---

## Virtual Networks

In addition to providing an easy way to test operating systems, VirtualBox also provides a way to test networks.

<div class="separator" style="clear: both; text-align: center;">
<a href="http://2.bp.blogspot.com/-SLJ-l9NQEa4/TrmZyK1DFwI/AAAAAAAAACI/P26EssI6igA/s1600/pfsense-virtual-network.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="306" src="http://2.bp.blogspot.com/-SLJ-l9NQEa4/TrmZyK1DFwI/AAAAAAAAACI/P26EssI6igA/s320/pfsense-virtual-network.png" width="320" /></a></div>

## Setup

### VirtualBox

Turn off VirtualBox's internal DHCP server (via Preferences).

1. Create a new guest on VirtualBox as a 64-bit FreeBSD instance. pfSense has very light resource requirements.
2. Assign 128Mb of RAM and 8Gb of storage.
3. Create two network interfaces. Both should be PCnet ll (`Am79C970A`)—FreeBSD has native support for these cards. One should be internal (`intnet`) and the other should be either NAT or Bridged.

### Install pfSense

1. Download [pfSense](http://files.chi.pfsense.org/mirror/downloads/pfSense-2.0.1-RELEASE-amd64.iso.gz). I used the [Chicago mirror](http://files.chi.pfsense.org/mirror/downloads/).
2. Install using _Quick Install_.
3. Assign one interface `le0` to WAN and the second, `le1`, to LAN.
4. Then point your browser (from a machine on your internal network) to <https://ipaddress>

You may want to change the subnet for your experimental network. I use `172.16.50.1` to avoid colliding with `192.168.x.x` and `10.0.0.0` networks that are more common.

<div class="separator" style="clear: both; text-align: center;">
<a href="http://1.bp.blogspot.com/-KPbCUU2h-jo/TvU8i8lwWUI/AAAAAAAAADs/gQ6ZB-CX-Is/s1600/pfsense-172.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="93" src="http://1.bp.blogspot.com/-KPbCUU2h-jo/TvU8i8lwWUI/AAAAAAAAADs/gQ6ZB-CX-Is/s320/pfsense-172.png" width="320" /></a></div>

pfSense also includes a DHCP server by default. If you are testing DHCP services on your internal network, be sure to turn it off. It's listed under _Services_.

Finally, if you are running DHCP on your lan (host machine network), you may want to set up a DHCP lease reservation for the WAN interface to ensure you always get the same IP address for your experimental network.

### Set Static IP on Ubuntu

If you are going to run `DHCP` on your experimental network, you'll need to assign a static ip to your `DHCP` server. Edit `/etc/network/interfaces`

    auto eth0
    iface eth0 inet static
        address 192.168.1.100
        netmask 255.255.255.0
        network 192.168.1.0
        broadcast 192.168.1.255
        gateway 192.168.1.1

Note that your values may differ. Then restart networking

    $ sudo /etc/init.d/networking restart

### Set Full Hostname on Ubuntu

Edit `/etc/hosts` to provide your machine with a fully qualified domain name:

    127.0.0.1   stemsrv01.lab.lan stemsrv01 localhost
    127.0.1.1   stemsrv01.localdomain   stemsrv01

_Note that order matters._ See the [following post](http://praxis.rocketknowledge.com/2011/12/machine-names.html).

### Port Forwarding

You may want to access the machines on your experimental network via SSH. To enable this, you'll need to turn on port forwarding on pfSense. But before you do, make sure you uncheck _Block private networks_ on your WAN interface settings.

<div class="separator" style="clear: both; text-align: center;">
<a href="http://4.bp.blogspot.com/-go2_2DcdTCk/TvVRWOnyp0I/AAAAAAAAAD8/x-aXOX0X6SM/s1600/pfsense-private-networks.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="225" src="http://4.bp.blogspot.com/-go2_2DcdTCk/TvVRWOnyp0I/AAAAAAAAAD8/x-aXOX0X6SM/s320/pfsense-private-networks.png" width="320" /></a></div>

Then go to Firewall -> NAT and create a new port forwarding rule (in this case, forward WAN port 2222 to 22 on an internal host).

<div class="separator" style="clear: both; text-align: center;">
<a href="http://1.bp.blogspot.com/-3nWFTEkXFno/TvVXoPo4VZI/AAAAAAAAAEE/aVUfff5HFPg/s1600/pfsense-port-forward.png" imageanchor="1" style="margin-left: 1em; margin-right: 1em;"><img border="0" height="102" src="http://1.bp.blogspot.com/-3nWFTEkXFno/TvVXoPo4VZI/AAAAAAAAAEE/aVUfff5HFPg/s320/pfsense-port-forward.png" width="320" /></a></div>

