# IPsec

## StrongSwan
StrongSwan is an open source IPsec-based VPN 

It has currently two ways to using ipsec.conf or swanctl.conf.
What I currently have configured for my VPN uses the deprecated ipsec.conf option.
I will likely switch to the newer swanctl.conf way, but their doesn't seem like 
there is any difference between the two except file parsing.

## OpenIKED
OpenIKED is another IPsec-based VPN option. 
It is integrated as part of OpenBSD. 

I haven't set this up but would like to try and create a tunnel between some OpenBSD systems I have.
I probably won't use this for any useful functionality but would like to learn another system.
Then, I can figure out which I prefer to utilize and are easier to set up. 
