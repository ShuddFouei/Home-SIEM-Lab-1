# Home-SIEM-Lab-1
Homelab utilizing Wazuh for SIEM and EDR, Kali for attack, and VM endpoints

This repository serves to document the creation of this lab for future iterations and fast setup, as well as explore alternative options for software utilized. 


------------------------------------------------------------------------------------------------------------------------
SETUP:
Virtual Machines & basic function: 
  - Kali Virtualbox Image - https://www.kali.org/get-kali/#kali-virtual-machines
  - Ubuntu 22.04 Desktop w/ Wazuh server / manager / indexer https://documentation.wazuh.com/current/quickstart.html
  - Ubuntu 22.04 server run headless - https://ubuntu.com/download/server
  - Metasploitable 3 Virtual environment to be attacked & generate telemetry - https://github.com/rapid7/metasploitable3
  - Windows & Ubuntu stock VM to test default vulnerability

Within Virtualbox: 
  1. Tools > Network > NAT Networks
  2. Create Network
  4. Each VM to be monitored should then be put on this NAT network (Settings > Network > Attached to Nat Network)

Wazuh Setup:
Wazuh's setup is extremely self explanatory, and can be followed via the official documentation. However, as guidelines:
DASHBOARD & SERVER
  - On the Ubuntu Desktop designated to be the Wazuh Server, run the install lines in the terminal
    - NOTE: WAZUH IS LARGE AND REQUIRES SPACE FOR ITSELF AS WELL AS LOG STORAGE - CONSIDER FOLLOWING WAZUH'S SIZE GUIDELINES DEPENDING ON SCALE OF THIS PROJECT
  - Upon conclusion, copy password down within terminal & go to the IP of your machine via web browser URL
  - Log in with given information and ensure the dashboard is operational
  - navigate to [your wazuh IP]/app/endpoints-summary# and click Deploy New Agent
  - Follow the instructions and run commands on endpoint VMs to create your SIEM network!
------------------------------------------------------------------------------------------------------------------------

GOALS : 

  - SIEM:
    - Note patterns of attack
    - create rules & alerts
    - follow built-in guidelines to gain understanding of best practices & legal guidelines
    - create graphs & visualizations
  - Kali
    - Become familiar with tools used to scan & attack machines
    - See what generates lots of noise on Wazuh dashboard vs what can be more quiet
    - Metasploit Metasploitable as much as possible - log flags for personal achievement
    - Become leet hacker
  - Metasploitable / victim endpoints
    - Patch systems via Wazuh or learned best practice
    - Utilize tools to detect, prevent, respond or remedy attacks
    - IF IN INTERNAL NETWORK - run malware or install random files to sandbox and observe (may need to use splunk)
------------------------------------------------------------------------------------------------------------------------

  TODO:
    -Wait for Win11 dev images to be put back up (down since 10/23/2024)
    -Sandbox install Metasploitable 3 & clone VM image 
