# Exercise 4: Azure Stack HCI Vm provisioning

### Task 1: Create a Logical Network for Azure Stack HCI VM.  

1. Navigate to the Resource Group in the Azure portal navigation section.

   ![](.././media/navigate-resource-group.png "Select Resource Group from Navigate Option")

2. From the Resource groups pane, click on **AzureStakHCI** resource group and verify the resources present in it.

   ![](media/azurestackhci-rg.png "Select Azure Stack HCI Resource Group")

3. In the  **AzureStakHCI** resource group in the search bar search for **hciboxcluster** **(1)** and select **hciboxcluster** **(2)** Azure Stack HCI.

   ![](media/selecth-ciboxcluster-hci.png)

4. In the **hciboxcluster** Azure Stack HCI, from the left menu select **Logical networks** **(1)** under Resources, and click on **+ Create logical network** **(2)**.

   ![](media/logic2network-create.png)

5. In the **Create logical network** tab, under Basic fill the fallowing details and click on **Next: Network Configuartion** **(5)**.

    - Subscription : Default subscription **(1)**
    - Resource group : **AzureStackHCI** **(2)**
    - Logical network name: **hcibox-vm-lnet-vlan200** **(3)**
    - Virtual switch name: **ConvergedSwitch(hci)** **(4)**

      ![](media/logic-2network-basic.png)

6. In the **Network Configuation** tab, under the fallowing deatils and click on **Next: Tags** **(7)**.

    | **Variables**                | **Values**                                                    |
    | ---------------------------- |---------------------------------------------------------------|
    | IP address assignment | **Static** **(1)** |
    | IPv4 address space    | **192.168.200.0** **(2)** from the drop down  address prefix select **\24** **(3)** |
    | Default Gateway       | Enter Default Gateway address as **192.168.200.1** **(4)** |
    | DNS Servers           | Enter DNS Servers **192.168.1.254** **(5)** |
    | VLAN ID               | Enter **200** **(6)** | 

      ![](media/logic-2network-network.png)

7. In the **Tag** tab, leave it as default and click **Next: Review + Create**.

8. In the **Review + Create** tab, click on on **Create** button.

   ![](media/logic-2network-create.png)

### Download and Add the VM image to Azure Stack HCI Storage.

1. In the **hciboxcluster** Azure Stack HCI, from the left menu select **VM Image** **(1)** under **Resources**, click on **+ Add VM Image** **(2)**, and click on **From Azure Marketplace** **(3)**.

   ![](media/vmimage-creat.png)

11. In the **Create an image** tab, enter the fallowing details and click on **Review + Create** **(6)** button.

    - Resource group : **AzureStackHCI** **(1)**
    - Save image as: Enter Image name as **hci-vm** **(2)**
    - Custom location: From the drop-down select **jumpstart** **(3)**
    - Image to download: Select **select Windows 10 Enterprise multi-session, version 21H2 - Gen2** **(4)** VM image.
    - Storage path: select **Choose automatically** **(5)**

      ![](media/vmimagebasic.png)

11. In the **Review + Create** tab, click on **Create** button.

    ![](media/vmimagecreate.png)

    > **Note**: VM images download may take upto 1 hour.