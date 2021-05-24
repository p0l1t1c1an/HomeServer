# OpenIKED
The IKE v2 daemon on openbsd reads a config file at `/etc/iked.conf` and reads for certs and keys under `/etc/iked/`

### iked.conf 
The iked.conf file is the only config file need for the iked. This was far easier to set up than StrongSwan.
Mainly due to the really well made man page on OpenBSD for this.

```
active | passive - Should iked attempt to initiate a connection.

from X.X.X.X/X | dynamic | any - Your local subnet any will use 

to X.X.X.X - The local subnet on the foreign side

peer/local X.X.X.X - peer is the public addr of the remote connecting to  
                     and local is this device's public address 

ikesa/child  enc 'cipher' prf 'psuedo-rand auth' group '(modp/ecp/...)'
- This specifies the encrytion (enc), psudeo random authentication (prf), and 
  DH groups (group) for both IKE negotitation and ESP

srcid/dstid  fqdn - This is used as the name the of the foreign/local device 
                    The foreign id is used to locate the public key of said sevice

request address X.X.X.X | dynamic - This lets the local device get an ip addr to assign 
                                    to the iface (below). (Used to prevent use of NAT in pf)

iface enc0 - The interface used for encapsulating and deapsulating traffic

```
### /etc/iked 
Inside the /etc/iked directory their are directories for public keys/certs and private keys
as well a local.pub key. The local.pub key is used as this devices public key. As local.key, 
in the private directory used as the local.key used as the private key. Finally, under pubkeys,
there are directories fqdn and ipv4 (plus some more). This is where the foreign public key must go.
It should be named the same as the `dstid` and should be in the respective location. So if the `dstid`
is a domain name it should be under fqdn and if it is an ip it should be under ipv4.
