manage-openvpn
==============

This is a simple script to install an OpenVPN server and add/remove users (using mutual certificate authentication only). This is a fork from [Nyr/openvpn-install](https://github.com/Nyr/openvpn-install), which removes all user interactions, in order to be able to install it in batch (please note adding users still requires some interactions).

Run the following on the machine you want to use as your OpenVPN server:
$ wget https://raw.githubusercontent.com/solomonudoh/openvpn-install/master/manage-openvpn.sh
$ chmod +x manage-openvpn.sh
$ sudo ./manage-openvpn.sh -i

Don't forget to enable NAT! Example on a Linux box:

    $ sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
    $ sudo apt install iptables-save iptables-persistent
    $ sudo iptables-save > /etc/iptables/rules.v4

