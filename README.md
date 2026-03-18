# T-Pot Honeypot Deployment and Attack Monitoring

## Overview

This project focused on deploying a *T-Pot* honeypot in a cloud-hosted *DigitalOcean* droplet and monitoring real-world attack activity against it. The goal was to gain hands-on experience with honeypot technology, understand how internet-exposed systems attract traffic, and observe attacker behavior through the T-Pot dashboard and Kibana.

I had been interested in honeypots for a while because I wanted to see how they actually worked in practice. This project gave me a way to move beyond theory and interact with real attack telemetry in a controlled environment.

---

## Objective

The main objective of this lab was to:
- Deploy a publicly reachable T-Pot honeypot in the cloud
- Access and manage it remotely using SSH from PowerShell
- Monitor attack activity through the T-Pot web interface
- Review events in Kibana to identify brute-force attempts and targeted services
- Build foundational experience in threat monitoring and honeypot analysis

---

## Environment

Platform: DigitalOcean

Instance Type: 4 vCPUs, 8 GB memory, 50 GB SSD

Deployment Type: Cloud-hosted droplet

Management Method: SSH from local machine using PowerShell

Honeypot Platform: T-Pot

---

## What T-Pot Is

T-Pot is an all-in-one honeypot platform that combines multiple honeypot services with monitoring and visualization tools. It is designed to collect attack activity from internet-exposed services and present that data through dashboards and analytics tools.

## Project Workflow

1. Provisioned the cloud environment

I first created a DigitalOcean droplet to host the honeypot. This allowed the system to be internet-facing and capable of receiving unsolicited traffic from external hosts.

2. Connected remotely from my local machine

I used PowerShell on my local computer to connect to the droplet over SSH. My PowerShell usage in this lab was primarily focused on remote administration and installation.

3. Installed T-Pot from the GitHub repository

Using SSH commands from PowerShell, I installed T-Pot from its GitHub-hosted files. Public installation references for T-Pot describe a setup flow that includes installing Git, cloning the T-Pot repository, running the installer script, and rebooting the system once installation is complete.

4. Created a user account manually

As part of the setup process, I manually created a user named 'shane' for access and management.

5. Reconnected using the new SSH port

After installation, T-Pot automatically changed the SSH port from the standard port 22 to 64295. References discussing T-Pot do confirm that this port change is part of the normal deployment behavior. I accessed the system using:

ssh -p 64295 <public-ip>

This matched the post-installation behavior I observed in my lab.

6. Accessed the web dashboard

After T-Pot finished installing, I accessed the dashboard through:

https://<public-ip>:64297

This gave me access to the T-Pot interface containing tools such as the: 
- Attack Map
- CyberChef
- Elasticvue
- Kibana
- Spiderfoot

7. Monitored live attack data

Once the honeypot was live, I began reviewing incoming activity through the dashboard. I first used the attack map for a high-level view, then moved into Kibana to inspect attack attempts in more detail.

Step-by-Step Lab Notes

This section is written to reflect the setup flow I followed as closely as possible based on my own actions and the referenced tutorial. [Tutorial I Followed](https://www.youtube.com/watch?v=KKu8CnTkcY0).

---

## What I Observed

I didn't exactly know what I was looking at at first, but within about 20 minutes, the honeypot was already receiving a noticeable amount of activity. I observed traffic from multiple countries, including:

- United States
- Romania
- United Kingdom
- France

My first impression overall impression was excitement as I couldn't believe I was seeing real attacks. I also noticed that a large portion of this traffic appeared to be automated bot activity, especially because in Kibana some of the username and password fields appeared as null. I would only see brute-force attempts in a SSH attack. 

I returned the next day after letting the honeypot continue overnight, and I was able to observe more attack types and review them in more depth through Kibana.

## Attack activity observed

- SSH brute-force attempts
- SMB-related activity
- MySQL-related activity
- SQL-related activity
- Telnet activity
- RPC activity
- HTTP activity

This, to me, was one of the most interesting parts of the lab because it showed how quickly publicly exposed infrastructure begins attracting opportunistic scans and automated attack attempts.

---

## Analysis Experience

The most valuable part of this project was not just installing the honeypot, but learning how to interpret what I was seeing once the data started coming in.
At first, I did not fully understand everything happening during setup. I only began understanding the environment better once the deployment was complete and I could start reviewing the attack telemetry myself.

---

## Key Skills Demonstrated

- Honeypot deployment
- Cloud-hosted environment cybersecurity lab setup
- Remote administration with SSH
- Internet exposure and unsolicited attack traffic
- Attack surface monitoring
- SSH brute-force observation
- Threat telemetry review in Kibana
- Basic event analysis and service targeting awareness

---

## What I Learned

This project taught me several important lessons:

1. Internet-exposed systems receive traffic very quickly

One of my biggest takeaways was how fast attack traffic appeared. The honeypot did not need to be online for long before it began receiving connection attempts.

2. Much of the activity is automated

A large amount of the traffic appeared to come from bots performing broad scanning and automated login attempts rather than targeted, manual attackers.

3. Attackers probe many services, not just SSH

Before this lab, I mainly associated internet-facing attacks with SSH brute force. After reviewing the data, I saw activity across several protocols and services, including SMB, Telnet, MySQL, HTTP, RPC, and SQL-related traffic.

4. Visualization tools make security data easier to interpret

The T-Pot dashboard and Kibana made it much easier to move from “something is happening” to “I can identify what services are being targeted and how.”

## Challenges

This project was successful, but one honest takeaway is that I did not fully understand every installation step while I was doing it. I followed the tutorial exactly and gained the most understanding after the system was already running and I could analyze the collected data.

That said, this was still valuable because it reflects a real learning process.

---

## Personal Reflection

This was one of the most exciting labs I have done so far. My immediate reaction after seeing real attack traffic was:
I think this is insanely awesome. The fact that real machines are trying to attack me and it’s not a little amount of them either. That reaction and initial excitement is what made this project stand out to me. It turned a concept I had only heard about into something I could actually deploy, monitor, and learn from in real time.

--- 

## Future Improvements

I will continue building on this project, possible next steps include:

- running the honeypot longer to collect more data and possibly creating a database in *Elasticvue*
- documenting repeated IPs, ports, usernames, and attack patterns
- comparing attack volume across time periods
- adding firewall controls and documenting their effect
- performing deeper Kibana analysis and creating custom visualizations
- studying which T-Pot components generated which logs

## Relevant Images
<img width="1911" height="887" alt="SS3(Honeypot)" src="https://github.com/user-attachments/assets/3a908025-8a82-48fd-97ca-50fbdff75cb1" />
<img width="1902" height="827" alt="SS4(Honeypot)" src="https://github.com/user-attachments/assets/17400c8d-8fc3-421e-8fca-29b24db04c86" />
