---

title: "Laying Groundwork"
date: 2025-12-25 23:51 -0500
categories: [homelab getting started]
---
	
For some financial and spiritual reasons, I find myself in a spot to start documenting my process of learning how to build servers and self-host a lot of things I've always been curious about. Some of my lnoger term goals include hoosting a Matrix server for a youtube series I help with. Some mid term goals include self hosting notes tools like obsidian and calendars. For now I have some pretty straightforward goals that I'm looking forward to picking away at

## First Goals

 - Learn how to maintain a dev blog with git
 - Configure my Mikrotik router with ProtonVPN  
 	 - port forwarding for torrent seeding  
	 - VPN tunneling into my LAN
 - Set up a Raspberry Pi as a seedbox and learn how to use the web GUI  
 - Run a [copyparty](https://github.com/9001/copyparty/) server on said Raspberry Pi  
 
The real challenge will be trying stay focused on these goals as one problem leads to the next. "How to setup VPN tunneling" turns into "How doees a bridge work" which turns into learning about the inner guts of packets etc etc. In the process I find out that 'actually a raspberry pi won't do what I need for such and such reason' and suddently I'm shopping for ThinkCentres. In order to keep me on track, I came up with some constraints

## Rules

 - No more hardware. I already have everything I need.  
 - No watching long ass youtube tutorials. Documentation, forums, my friends and Claude are more than enough. Youtube is designed to make you jump around from vid to vid like a psycho. I just can't trust my attention span.  
 - Don't get stuck reading wikipedia articles about network design and super low-level information. I'm not a professional network engineer or IT admin. I'm a musician who is also a big ass nerd and does some light networking for video engineering work. 
 - Start a new post.md and outline the task before sitting down to work. This way I'm starting with documenation and I have a nice place to park questions instead of running off down a wikihole. 
 - Time spent on Homelab can't exceed time spent on guitar in a day. In other words, if there's no time to practice guitar, then there isn't time to work on homelab. I can write, meditate, or just stare into space, but I can't use this to procrastinate on my craft. This will probably be the hardest rule and I may have to refine this rule later. 
 
 
Even with these constraints there's a lot of freedom to mess around. If today I want to setup DHCP reservations for all my devices and tomorrow I want to make a goofy custom mouse cursor for my blog that's 100% ok, as long as I'm documenting the process. I already know I'll be relying on Ben for a lot of help, and he has strongly encouraged me to take advantage of Claude. They guided me through the set up of this git. I've never actually learned how github works, but I know it's crucial for getting this whole project running so this is the first step. Lot of YAML formatting I'll probably have to learn over time, and some front end design.


The first step of setting up RouterOS will be a tought beginning, but as long as I can resist the urge to understand every aspect of the OS at once, I should be ok. This was a good start, here's to my first commit!