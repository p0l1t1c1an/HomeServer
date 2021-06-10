# HomeServer
A repo to document my homeserver and how to config and utilize these software running on it. 

### How Documention is Handled

#### Software, Services, and Config Files
- In this repo, I will create directories called the software/service, s/s, running on the server
  - These directories will contain a Readme and config files for the the s/s
  - The Readme will go over the ideas of the s/s and describe the config files purpose
- The s/s may not be what is permanently running on my FreeBSD server
  - Much of these, are for me to mess around with and get to understand how they work
  - Then, if I want to reuse them, I have easy access to descriptive configurations and details 

### Plan of Action
- As of right now, I thinking of swapping out FreeBSD with SmartOS and using it as a hypervisor. 
  - What I like:
    - SmartOS has quite a few things I'm familiar with on BSDs like bhyve
    - Has an advanced system of Solaris' Zones/Containers that inspired by FreeBSD's jails
    - Supports "Linux" containers by mimicking/emulating Linux syscalls so I won't need VMs if using something like docker  
    - ZFS, which I absolutely love, but also other Solaris tools that I would love to learn like Crossbow and DTrace
  - What I dislike:
    - SmartOS wants to flex that it has KVM but also states that bhyve runs better so I'm a little confused about that
      - My guess is KVM was first done by SmartOS then illumos ported bhyve, so now SmartOS has both 
    - I think it uses iptables, but I really like and am very familiar w/ pf 
- In the near future, maybe post-graduation, I want to "retire" this device and use it a desktop
  - Then, I want to get the in homelab game with like 2-3 old rack servers, a NAS, and nice router
  - Potential Services: 
    - IPSec VPN to access private services and data
    - Public website and blog
    - Mail with anti-spam and the rest of the works 
    - DNS + DNSCrypt and add it to the public list of DNSCrypt servers 
    - Cgit/Gitlab instance and then just mirror to github
    - Fuzzing VMs or Folding@Home / a similar distributed research system
