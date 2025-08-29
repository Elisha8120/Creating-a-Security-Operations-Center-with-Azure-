# Creating-a-Security-Operations-Center-with-Azure-
I will be demonstrating how to create an at home Security Operations Center, and using a "Honey Pot" VM open on the network as bait to catch real live traffic.  



# Steps Overview 
1. I will very briefly go over setting up the virtual enviorment using Azure.
2. Next I will demonstrate how to configure log forwarding into a central repository.
3. Next we connect the repository into a SIEM, being able to query into SIEM
4. Create an attack map that shows where attackers are attacking from. 



# Azure Virtual Enviorment Setup

First created the resource group so that when we create the Virtual machine and Virtual Network we have a Resource group already made to attach it to. Something important when creating a virtual enviorment in azure, try to ensure that all the tools are created in the same region. In this case for this project we went ahead had no inbound rules and allowed any connection from anywhere allowing our machine to be on the internet and be visable to anyone. 



<img width="1327" height="293" alt="image" src="https://github.com/user-attachments/assets/08852fe0-e33c-4f6e-9852-2f23ba7d2afd" />

<img width="1881" height="684" alt="image" src="https://github.com/user-attachments/assets/41dc8a68-55a1-4569-9998-346df355f842" />









