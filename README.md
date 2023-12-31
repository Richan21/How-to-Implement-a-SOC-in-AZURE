![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/84cb0c29-1786-4e7b-9342-860a3b4dde9d)

<h1>Azure SOC and Honeynet Setup Guide</h1>
The guide outlines setting up a Security Operations Center (SOC) and Honeynet on Azure, emphasizing effective monitoring, incident response, and honeypot deployment to bolster your organization's resilience against cyber threats <br />


## Prerequisites
1. Create an Azure Subscription to access the Azure Platform. This comes with an initial $200 credit for new accounts.

<h2>Environments and Technologies Used</h2>
(NOTE: I was able to set up the entire project on both my IPAD Pro 2020 and desktop running Windows 10)

- Microsoft Azure (Virtual Machines/Compute)

## Resource Group Creation
1. Sign in to the Azure Portal.
2. Navigate to “Resource groups.”
3. Click “+ Add” to create a new resource group.
4. Fill in the basics:
   - Subscription: Choose Azure subscription.
   - Resource group: Enter a unique name.
   - Region: Choose the deployment region.
5. Review and create the resource group.

![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/793d928e-f636-43bc-8f46-b61191a2fe94)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/8208fb19-952d-4345-bc71-26c79d74b0b7)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/0fd5d018-52c9-45fa-91b1-4dd2d4c805d7)

## Virtual Machines (VM)
1. Navigate to “Virtual Machines”
2. Click “+ Add” to create a new Virtual Machines.
3. Fill in the basics:
   - Subscription: Choose Azure subscription.
   - Resource group: Create or select.
   - Virtual Machine name: Enter a unique name.
   - Region: Choose the deployment region.
4. Proceed to Networking settings.
   - NIC network security group: select Advanced.
   - Configure Network Security group: Select "Create new" below the dropdown options.
   - Delete existing Inbound Rules (Trashcan far right).
   - Select + Add and Inbound Rule.
   - Fill in the Source port ranges & Destination port ranges with an * instead of a number.
   - Lower Priority number down to 100.
   - Optional, you can change name of this Security Rule.
   - Add when done.

6. Create the Virtual Machine.

![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/3a2baf83-9253-4cda-810c-638bb234791c)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/6f0ceddc-a6a9-4575-b856-4761ed5a5ea0)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/86d47af9-28ed-4f5e-8a35-af6967915736)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/4505eace-ef7c-4703-815b-c5d8927406b2)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/81930f28-3ebc-4551-894c-2ba4fa4f226a)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/c4060068-a848-4705-a1b9-0495f836ba52)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/7f8d09d8-ae39-4857-8386-21217fe34bc3)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/fd8438d9-4263-4ac5-b0d2-df5c205972dc)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/d023c5c1-b66f-4317-ba99-851b2891776f)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/726c6b5a-c4dc-4e49-ab78-d130428e5d8c)


## Log Analytics Workspace
1. Navigate to “Log Analytics.”
2. Click “+ Add” to create a new Log Analytics Workspace.
3. Fill in the basics:
   - Subscription: Choose Azure subscription.
   - Resource group: Create or select.
   - Workspace name: Enter a unique name.
   - Region: Choose the deployment region.
4. Configure settings and review.
5. Create the Log Analytics Workspace.

![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/c7540f6b-20c0-45fa-8173-7dbea2264f6e)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/79f3c74f-d429-4984-a217-1bee30d4b40e)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/3c5caa4d-756c-42b4-b83c-d0e250b4ded2)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/6e3d026b-6ade-4935-9648-6195e183a51f)

## Microsoft Defendor for Cloud Settings
1. Go to Microsoft Defendor for Cloud.
2. Navigate to Overview.
3. Under Management (option on far left), select Environment Settings.
4. Select the Log Analytics work space 
5. Servers must be turned "On" and SQL servers on machines myust be turned "Off".
6. Save changes.
7. Go to Data Collection and select "All Events"  then Save.

![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/8598f16d-bc07-4f81-9a97-be7371c405db)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/bbd99ee3-66cf-460b-bede-7a711f4450a4)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/2afa98af-a5c5-4784-b66f-500787b2ed55)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/1d42075f-4ecf-4270-a610-8b72a9116225)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/c242cbb4-0735-40d5-994a-500ed10695b2)


## Connecting Log Analytics workspace to VM
1. Connect to Log Analytics Workspace.
2. Select Log Analystics workspace.
3. Go to Virtual Machines and Select VM.

![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/e67c4b3f-c8dd-47e9-9459-4f0091bae3bb)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/77e80804-32f2-456b-9b81-01b87103f855)
![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/d59abb5a-2210-4454-b5b4-6d82bd753ae2)



## Azure Sentinel Configuration
1. Go to Azure Sentinel.
2. Create a new workspace if needed.
3. Navigate to “Configuration.”
4. Connect to Log Analytics Workspace.
5. Ingest and analyze data.
6. Configure connectors for data sources.
7. Enable Common Data Model (CDM).
8. Review and save settings.
9. Monitor Azure Sentinel Dashboard.

![image](https://github.com/Richan21/How-to-Implement-a-SOC-in-AZURE/assets/153684298/cf212206-e04b-450d-93dd-d3f12a59d06e)

## Honeynet Setup
1. Consider creating a separate Azure subscription for the Honeynet.
2. Create a Resource Group for Honeynet resources.
3. Create a Virtual Network:
   - Define address space and add a subnet.
   - Configure NSG settings.
4. Create Virtual Machines:
   - Choose OS, size, and configure settings.
   - Review and create the VM.
5. Create Network Security Groups (NSG):
   - Define inbound and outbound rules.
6. Implement monitoring and logging.
7. Use deception technologies like honeypots.
8. Perform regular updates and maintenance.
9. Analyze incidents and attacks in the Honeynet.
10. Ensure compliance, continuous improvement, and training.

## Important Considerations
- Compliance: Ensure SOC and Honeynet comply with regulations.
- Continuous Improvement: Regularly update based on evolving threats.
- Training: Train SOC personnel and stakeholders on security practices.
