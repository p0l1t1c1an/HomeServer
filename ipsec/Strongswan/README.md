# Strongswan

### Configuration 
Strongswan's IPSec vpn reads a few configuration files. The following are a few key configuration options that I think are vital to the functionality of the vpn. 


#### ipsec.conf
The ipsec.conf file is main configuration file for the vpn.
In this config, left means local and right means remote.
This can be thought of as client/server model in a roadwarrior setup like I have.
But could also be tunneling two routers where that idea doesn't make sense. 
Both configs need match but inversed on the two machines establishing a tunnel.

`left/right = X.X.X.X | %any`

`left/rightsubnet = X.X.X.X/X`

`left/rightsourceip = 192.168.X.X/X | %config`

`ike/esp = <cipher>`

`type = tunnel | transport`

`forceencaps = yes | no`

`auto = start | add | route`


#### ipsec.secrets
This file tells strongswan what is the secret key for authentication. 
This can be a password being the Preshared Key (PSK) that both devices know beforehand.
Or it can be your devices private key when you know the other devices public key.

`: RSA key.private`

`: PSK "Secret Passphrase"`

#### strongswan.conf
This file is mainly used for configuring strongswan's ike daemon, charon. 
It default provides a system to dynamically load modules for different encryption systems.

`install_routes = yes | no` 

`initiator_only = yes | no`



