# Pi-Hole_DNS-Server_Raspberry-Pi5
## Set up Pi-hole DNS Server on Raspberry Pi 5  
## By Md Muhtashim Jahin  
### Goodbye Ads, Hello Privacy: Setting Up a Pi-hole on Raspberry Pi 5.  
Pi-hole is a lightweight DNS sinkhole that blocks advertisements and trackers across your entire network. It works by acting as a local DNS server that intercepts DNS requests and blocks any known ad-serving domains. The result? Clean, ad-free browsing and better security.  
Unlike browser-based ad blockers, Pi-hole works at the network level, protecting all devices—including smartphones, smart TVs, and IoT systems—without requiring software installation on each device.  
#### Project Overview
- Hardware: Raspberry Pi 5  
- Objective: Create a reliable DNS server to block ads and improve network performance  
- Software: Raspbian (Debian-based OS), Pi-hole  
- Purpose: Create a DNS sinkhole to block ads, reduce unwanted traffic, and enhance network security.    
- Network Role: Pi-hole IP set as the DNS server for my personal PC and optionally for other home devices.    
#### Step-by-Step Implementation    
1. Preparing the Raspberry Pi 5  
Flash the latest Raspberry Pi OS using Raspberry Pi Imager.  
Connect PI to wifi for internet access.  
Set a static IP on Network Adapter.  
2. Installing Pi-hole  
Use the command to install Pi-Hole  
``curl -sSL https://install.pi-hole.net | bash``  
Alternative Way: Clone GitHub repository and run  
``git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole  
cd "Pi-hole/automated install/"  
sudo bash basic-install.sh``  
Chose the interface with static ip for the DNS server.  
Opted for default blocklists (which can later be customized).  
Configured upstream DNS (Cloudflare in my case for privacy-focused resolution).  
Enabled logging and query analysis.  
Now, you can change the password from the Pi-Hole configuration file or stick with the random password it generated (you can see it in Terminal).  
3. Network Configuration  
Configured my PC’s DNS settings to point to the Pi-hole IP.  
Optionally updated my router to use the Pi-hole DNS for all connected devices  
4. Exploring the Admin Interface  
Accessible at http://<pi-ip-address>/admin  
Use your password to login.  
Real-time dashboard for monitoring:    
•	Total DNS queries  
•	Blocked requests  
•	Top clients and domains  
•	Forward destinations (upstream DNS)  
