---
layout: page
title: Personal Projects
subtitle: General overview of my personal projects with links to more details for each project
---

## Home server
Using some old computer parts I initially setup a home server using _Proxmox_ to host multiple different virtual machines each running something different. I experimented with _TrueNAS Scale_ to create a single large pool where I could safely store my files without relying on subscriptions services to one of the large tech giants. I ran different VMs including a _debian_ instance to SSH into for python coding and general tasks better suited for linux.

Since then I have switched to using the beta version of _Hex OS_, a tailored GUI for _TrueNAS Scale_ making simple tasks like setting up pools, users, and folder much easier but still allowing me to go into _TrueNAS Scale_ and set up apps and docker container, like _Immich_, _Portainer_, and a couple video game servers, allowing me easy management of the applications running and an easy way to update them when needed. I also setup a _debain_ VM for the same reason as above.

Being paranoid about the loss of family photos and personal files, I setup a second server using a pre-built chassis and identical hard drives so any data that is uploaded at either end is backed-up to the other location, so that there are at least 2 copies of the data at 2 different location, where each location would need to have 2 hard drives fail before any data loss. Redundancy is key but this setup is always evolving.