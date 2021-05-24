# IPsec
## StrongSwan
StrongSwan is an open source IPsec-based VPN 

It has currently two ways to using ipsec.conf or swanctl.conf.
What I currently have configured for my VPN uses the deprecated ipsec.conf option.
I will likely switch to the newer swanctl.conf way, but their doesn't seem like 
there is any difference between the two except file parsing.

#### Personal Issues w/ StrongSwan
I dislike the idea of strongswan having its own networking stack and a ton of other code.
It makes the program bloated and to me is a security risk because of it. 
I get that it makes itself more portable but it also means more mistakes. 
I ultimately think it should just have different ports to different OSes. 
That might also be easier to maintain. IDK. 

## OpenIKED
OpenIKED is another IPsec-based VPN option. 
It is integrated as part of OpenBSD. 

I have a preference for this over Strongswan as it seems far easier to set up. 
However, that thinking might be due to it not being my first time setting up an ipsec vpn.
I understand how it works better now compared to when setting up StrongSwan.

#### Personal Issues w/ OpenIKED
I don't know how to set it up, so I can have an encrypted private key to use on my device.
This way to connect to my vpn you need have a password plus the keys themselves.
There may be a way with ikectl but I have yet to find out how.
