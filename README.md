# Creating-a-Security-Operations-Center-with-Azure-
I will be demonstrating how to create an at home Security Operations Center, and using a "Honey Pot" VM open on the network as bait to catch real live traffic imitating the real life experience of capturing traffic from the network to my Virtual Machine. 



# Steps Overview 
1. I will very briefly go over setting up the virtual enviorment using Azure.
2. Next I will demonstrate how to configure log forwarding into a central repository.
3. Next we connect the repository into a SIEM, being able to query into SIEM
4. Create an attack map that shows where attackers are attacking from. 



# Azure Virtual Enviorment Setup

First created the resource group so that when we create the Virtual machine and Virtual Network we have a Resource group already made to attach it to. Something important when creating a virtual enviorment in azure, try to ensure that all the tools are created in the same region. In this case for this project we went ahead had no inbound rules and allowed any connection from anywhere allowing our machine to be on the internet and be visable to anyone. 



<img width="1327" height="293" alt="image" src="https://github.com/user-attachments/assets/08852fe0-e33c-4f6e-9852-2f23ba7d2afd" />

<img width="1881" height="684" alt="image" src="https://github.com/user-attachments/assets/41dc8a68-55a1-4569-9998-346df355f842" />


# Creating and Connecting the Log Repository, Microsoft Sentinel, and the Virtual Machine 

I first created the log analytics workspace(LAW), then I bought the Microsoft Sentinel (SIEM) subscription, which I linked my log analytics workspace to. 


<img width="1898" height="396" alt="image" src="https://github.com/user-attachments/assets/bf474831-79f5-4b1a-827d-2c1f64491f5c" />


<img width="1731" height="520" alt="image" src="https://github.com/user-attachments/assets/094d7d72-6c83-4353-b287-68539c8fab9d" />



I then installed "Windows Security Events via AMA" the necessary extension that would allow me to recieve the logs from my virtual machine. 


<img width="587" height="497" alt="Screenshot 2025-08-29 122139" src="https://github.com/user-attachments/assets/ae1cf762-5167-491c-b7be-539c5549ad1e" />




<img width="1882" height="921" alt="Screenshot 2025-08-29 132815" src="https://github.com/user-attachments/assets/88b4468b-7d49-4164-9d3e-89919bac2193" />



Once created SIEM with the appropiate data collection rules, we then need to link our Log Repository to our SIEM



Breakdown: Create log anaylytics workspace, apply the SIEM (in this case Microsoft Sentinel) and then add our virtual machine to our log repository to be able to overview the logs. 
Once we have done to steps in order we are able to see the end result in the photo below where we are able to have access our event logs in Microsoft Sentinel. 


<img width="1589" height="865" alt="Screenshot 2025-08-29 141924" src="https://github.com/user-attachments/assets/49b4642a-ae8e-48ec-aca9-24c2da6b71bb" />




# Adding info to  Watchlist in Sentinel 

Noticebly in sentinel only information we can recieve is information on the events, time, accounts, etc. To have a fully set up Security Operation center we are missing information about our events/attackers location. So what I did was get a list of ipaddresses corresponding to their locations and apply it to sentinels watchlist to be able to have a fully functioning visable map. This takes the place of the real life scenerio where the location data would be coming from a live source or automatically.

<img width="1561" height="743" alt="image" src="https://github.com/user-attachments/assets/4831f746-93a2-4347-b603-6b7d0607363d" />



# Attack Map Creation and Finalization. 

Using a query I was able to get online, i'm able to copy the setting's as shown in the screenshot below. 

<img width="1879" height="852" alt="image" src="https://github.com/user-attachments/assets/a3f8e754-88cb-4984-9d0e-58b466613289" />


Above is how our map looks after 7 hours of being open on the network. 

We only got hits from Poland and Netherlands. 

Stats

Poland: 758 events

Netherlands: 1.38k Events 














