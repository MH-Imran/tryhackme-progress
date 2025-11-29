# What Is a Network? – TryHackMe Notes


This is my first room from the “Network Fundamentals” module. I kept my notes simple so I can come back to them quickly.



## What I Learned
- A network is basically a way for devices to talk to each other.
- Devices can share information, resources, or services through connections.
- Networks can be small (home network) or huge (the internet).
- Every device needs an identifier (an IP address) to communicate.


## Key Points (In My Own Words)
- The internet is just a giant network of many smaller networks.
- Networks help computers share files, send messages, and access websites.
- Without networks, security monitoring wouldn’t exist — no logs, no traffic, nothing to analyze.



## Why This Matters for SOC Work
Understanding what a network actually is makes it easier to understand:
- how attackers move from one device to another  
- why logs are generated  
- how traffic flows  
- what “normal” communication looks like  

All of this becomes important later in detection and investigation.



Very basic room, but it sets the foundation for everything that comes next.
 
  _**Completed**: Nov 28, 2025_







---








# Intro to LAN – TryHackMe Notes


## What I Learned
- How devices communicate inside a local network
- Role of switches and broadcast domains
- MAC addressing basics
- Difference between unicast, broadcast, and multicast
- How local network traffic flows
    
_**Completed**: Nov 29, 2025_



---




# OSI Model – TryHackMe Notes



I just finished the OSI Model room on TryHackMe, and these are basically the notes I took while trying to make sense of everything. I’m still wrapping my head around some parts, but this is what clicked for me so far:



## What I Understand So Far

- The OSI Model is basically a **7-step explanation** of how data moves from one device to another. I never really thought about how much happens behind the scenes until now.
- The lower layers (1–4) seem to deal more with “how stuff actually travels,” while the upper ones (5–7) feel more like “how apps and humans interact.” Not sure if that’s a perfect way to say it, but it helps me remember.
- Data goes **down the layers** when sending and **up the layers** when receiving. This simple idea made a lot of things suddenly make more sense.



## Layer Thoughts (My Own Words)

- **Physical Layer:** literally the wires and signals. Easy enough.
- **Data Link:** MAC addresses, frames… still need to get more comfortable with this, but I get the basic idea.
- **Network Layer:** IP addresses. This one I understand better because I’ve seen IPs a million times.
- **Transport Layer:** ports, TCP/UDP — feels very important for SOC stuff.
- **Session, Presentation, Application:** these three are still a bit fuzzy, but I know they’re more about how software and services talk to each other.



## My Real Takeaways

- Thinking of it as a “ladder” really helped.
- When I see logs in the future (like in a SIEM), I’ll probably be able to recognize which layer the problem is happening in.
- I haven’t memorized all the layers perfectly, but I honestly understand them better than before.
- This room didn’t feel difficult, but it exposed how much happens during normal network communication.



## What I Still Need to Review

- Difference between frames vs packets vs segments
- The three upper layers (5, 6, 7) — I understand them, but not confidently
- How the OSI layers map to real protocols (e.g., where HTTPS sits, where ARP sits, etc.)

_**Completed:** Nov 29, 2025_
