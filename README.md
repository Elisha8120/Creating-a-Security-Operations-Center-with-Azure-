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


# Adding our Log repositry to our virtual Cloud System. 

To create the Log repository in Azure we search for "Log Analytics Workspace" and that's what we will link to our Microsoft Sentinel (SIEM) to be able to view our information on our virtual Machine. 



<img width="587" height="497" alt="Screenshot 2025-08-29 122139" src="https://github.com/user-attachments/assets/ae1cf762-5167-491c-b7be-539c5549ad1e" />




<img width="1882" height="921" alt="Screenshot 2025-08-29 132815" src="https://github.com/user-attachments/assets/88b4468b-7d49-4164-9d3e-89919bac2193" />





Once we have created our Log Analytics Workspace and linked it to our SIEM, we then need to link our Log Repository to our SIEM.
Breakdown: Create log anaylytics workspace, apply the SIEM (in this case Microsoft Sentinel) and then add our virtual machine to our log repository to be able to overview the logs. 
Once we have done to steps in order we are able to see the end result in the photo below where we are able to have access our event logs. 


<img width="1589" height="865" alt="Screenshot 2025-08-29 141924" src="https://github.com/user-attachments/assets/49b4642a-ae8e-48ec-aca9-24c2da6b71bb" />
