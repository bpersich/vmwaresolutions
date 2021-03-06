---

copyright:

  years:  2016, 2018

lastupdated: "2018-05-25"

---

{:tip: .tip}

# Ordering new vSphere clusters

To deploy a highly customizable VMware virtualized platform, order a VMware vSphere cluster on {{site.data.keyword.cloud}}. Use this procedure to define a new VMware vSphere cluster.

This procedure guides you through VMware component selecting, {{site.data.keyword.cloud_notm}} Bare Metal Server settings, storage settings, and networking choices, to create a new cluster. After you place the order, the cluster configuration is captured so that you can come back and continue to scale out the cluster as needed. Once the order is completed, you can manually configure the VMware cluster based on your requirements.

## Requirements

Ensure that you completed the following tasks:
*  You configured the {{site.data.keyword.cloud_notm}} infrastructure credentials on the **Settings** page. For more information, see [User accounts and settings](../vmonic/useraccount.html).
*  You reviewed the requirements and considerations in [Requirements and planning for vSphere clusters](vs_planning.html).

## System settings

<!--**Important: Do not modify any values that are set during ordering and cluster deployment. Doing so can result in your cluster becoming unusable.**-->
You must specify the following system settings when ordering a new vSphere cluster.

### Cluster name

The cluster name must be unique within your account.

## Licensing settings

Select the VMware components to be ordered with your cluster, and specify the licensing option for the components.

### (For business partner users only) Component bundles

If you are a business partner user, you can select a component license bundle when ordering a new vSphere cluster. The available bundles are as follows:

Table 1. Business partner component bundles for vSphere clusters

| Bundle | Components                   |
|:-------------------------|:-----------------------|
| Standard with Management | vSphere Enterprise Plus, vCenter Server Standard, vRealize Log Insight, vRealize Operations Enterprise |
| Advanced                 | vSphere Enterprise Plus, vCenter Server Standard, vRealize Log Insight, vCloud Director, NSX Base |
| Advanced with Networking | vSphere Enterprise Plus, vCenter Server Standard, vRealize Log Insight, NSX Advanced |
| Advanced with Networking and Management | vSphere Enterprise Plus, vCenter Server Standard, vRealize Log Insight, vRealize Operations Enterprise, vCloud Director, NSX Enterprise |

You can also include the following additional VMware components to your order:
* VMware vSAN
* VMware Site Recovery Manager
* VMware vRealize Automation Enterprise

**Note:** Business partner users do not have the option to Bring Your Own License (BYOL). The **I will provide the license** option is not available when completing your order.

### (For non-business partner users only) Individual components

If you are a non-business partner user, you can select the following VMware components flexibly for your vSphere cluster:
* VMware vSphere Enterprise Plus
* VMware vCenter Server
* VMware NSX
* VMware vSAN
* VMware Site Recovery Manager
* VMware vRealize Automation Enterprise
* VMware vRealize Operation Enterprise
* VMware vRealize Log Insight

**Note:** The VMware vSAN component is not available when you order VMware vSphere Enterprise Plus 6.0. If you plan to use your own license for VMware vSphere Enterprise Plus 6.0, an {{site.data.keyword.cloud_notm}} infrastructure ticket will be opened on your behalf requesting that the vSphere licenses of the ordered {{site.data.keyword.baremetal_short}} are replaced with your provided licenses.

### Licensing options

You have the following options for licensing the selected VMware components:
* **Include license with purchase**: In this case, a new license for the VMware component is purchased on your behalf. A combined VMware license is generated to match the cluster size of the order.
* **I will provide the license**: In this case, you will use your own license for the VMware component.

If you choose to purchase any license, except for vSphere Enterprise Plus and vCenter Server, and you order multiple ESXi servers, an {{site.data.keyword.cloud_notm}} ticket is opened automatically on your behalf to combine license keys. You are responsible to follow up with the ticket to ensure that you use only the license keys that the DevOps team generates.

**Important**: Using individual license keys together with the combined license keys does not meet the payment requirements for the licenses you will need.

## Bare Metal Server settings

### Data center location

Select the {{site.data.keyword.CloudDataCent_notm}} where the cluster is to be hosted.

**Note:** If you select a vSAN component, the location list is filtered by SSD availablity.

### CPU Model

The following CPU models are available for {{site.data.keyword.baremetal_short}}:
* Dual Intel Xeon E5-2620 v4 / 16 cores total, 2.1 GHz
* Dual Intel Xeon E5-2650 v4 / 24 cores total, 2.2 GHz
* Dual Intel Xeon E5-2690 v4 / 28 cores total, 2.6 GHz

### RAM

The RAM options include 64 GB, 128 GB, 256 GB, 384 GB, 512 GB, 768 GB, 1 TB, and 1.5 TB. Options available depend on whether you selected the VMware vSAN component.

### Number of Bare Metal Servers

The number of ESXi servers that you want add to the vSphere cluster. All the ESXi servers share the same configuration.
* If you selected the VMware NSX component, a minimum of 3 servers is required.
* If you selected the VMware vSAN component, a minimum of 4 servers is required.

## Storage settings

For orders without vSAN, ESXi servers are ordered with a 12-disk chassis, with two disks for the ESXi operating system (OS).

For orders with vSAN, ESXi servers are ordered with a 12-disk chassis and four disks ordered: two for the ESXi OS and two reserved for caching. These settings are configured by default and cannot be changed. You can order more capacity disks by selecting **Disk Type and Size for vSAN Capacity Disks** and **Number of vSAN Capacity Disks**.

When you selected the VMware vSAN component for the cluster, specify the following settings.

### Disk Type and Size for vSAN Capacity Disks

This option is available only when you selected the VMware vSAN component.

The following disk types are available:
* 960 GB SSD SED
* 1.9 TB SSD SED
* 3.8 TB SSD SED (3.8 TB SSD SED drives are supported when they are made generally available in a data center)

### Number of vSAN Capacity Disks

This option is available only when you selected the VMware vSAN component. The disk quantity options include 2, 4, 6, and 8.

## Network interface settings

You must specify the following network interface settings when ordering a new vSphere cluster.

### Host name prefix

The host name is used for all bare metal server orders. It is recommended to use the host name for all management virtual machines, such as vCenter Server, NSX, and so on.

The host name prefix must meet the following requirements:
* The name must start and end with an alphanumeric character.
* Only alphanumeric and dash (-) characters are allowed.
* The maximum length is 10 characters.

### Subdomain label

The subdomain label must meet the following requirements:
*  Only alphanumeric and dash (-) characters are allowed.
*  The subdomain label must start and end with an alphanumeric character.
*  The maximum length of the subdomain label is 10 characters.
*  The subdomain label must be unique within your account.

### Domain name

The domain name is used for all {{site.data.keyword.baremetal_short}} and must meet the following requirements:
* The name must consist of two or more strings that are separated by period (.)
* Only alphanumeric and dash (-) characters are allowed.
* Each string must start with an alphabetic character and end with an alphanumeric character, and the last string can contain only alphabetic characters.
* The length of the last string must be in the range 2 - 24 characters.
* The length of other strings must be in the range 1 - 63 characters.
* The maximum length of the domain name is 189 characters.

### VLANs

Network settings are based on your selection of either **Order New VLANs** or **Select Existing VLANs**.

One public VLAN and two private VLANs are required for your cluster order. The two private VLANs are trunked into each Bare Metal Server.

**Order New VLANs**  
Select to order one new public VLAN and two new private VLANs.

**Select Existing VLANs**  
Depending on the {{site.data.keyword.CloudDataCent_notm}} that you selected, existing public and private VLANs might be available.

  When you select to reuse existing public and private VLANs, specify the VLANs and subnets:
  * **Public VLAN** is for public network access.
  * **Private VLAN** is for connectivity among the data centers and services within the {{site.data.keyword.cloud_notm}}.
  * **Secondary private VLAN** is for VMware features such as vSAN.
  * **Primary Subnet** is assigned to physical hosts for public network access.
  * **Primary Private Subnet** is assigned to physical hosts for management traffic.

**Important:**
* Ensure that the firewall configuration on the selected VLANs does not block the management data traffic.
* Ensure that all of the VLANs you select are in the same pod, because ESXi servers cannot be provisioned on mixed-pod VLANs.

**FortiGate Physical Appliance 300 Series HA Pair**

You can also select whether to include the FortiGate Physical Appliance 300 Series HA Pair to secure your cloud environment. For more information, see [Components and considerations for FortiGate Security Appliance on IBM Cloud](../services/fsa_considerations.html).

## Order summary

Based on your configurations, the estimated cost is instantly generated and displayed in the right pane. Click **Pricing details** at the bottom of the right pane to generate a PDF document that provides the estimate details.

## Procedure

1. From the {{site.data.keyword.cloud_notm}} Catalog, click **VMware** on the left navigation pane, and then click **VMware vSphere** in the **Virtual Data Centers** section.
2. On the **VMware vSphere on IBM Cloud** page, click **Create**.  
   Ensure that you are on the **Create New** tab and that **New cluster** is displayed in the **Cluster Configurations** list.
3. Enter the cluster name.
4. Select the VMware components:
  * If you are a business partner user, select a license bundle and any additional available VMware components.
  * If you are a non-business partner user, select the component, edition if any, and specify the licensing option.
  When you choose to bring your own license (BYOL) for VMware vSphere Enterprise Plus, an {{site.data.keyword.cloud_notm}} ticket is opened automatically on your behalf to request the default vSphere licenses on your ordered {{site.data.keyword.baremetal_short}} to be replaced with your provided licenses.   

    **Important:** You are responsible to follow up with the ticket to ensure that you replace the vSphere license on the newly ordered ESXi servers so that the {{site.data.keyword.cloud_notm}} infrastructure grants the cancellation of the initially provided {{site.data.keyword.cloud_notm}} infrastructure vSphere license charge. To replace your ESXi vSphere license, see [Configure License Settings for an ESXi Host](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.vcenterhost.doc/GUID-1B128360-0060-40F2-A6F0-43CD2534B034.html){:new_window}.

5. Complete the Bare Metal Server settings:
   1. Select the {{site.data.keyword.CloudDataCent_notm}} to host the cluster.
   2. Select the CPU model and RAM size.
   3. Specify the number of Bare Metal Server.
6. If you selected the **VMware vSAN** component, complete the vSAN storage settings by selecting the **Disk Type and Size for vSAN Capacity Disks** and **Number of vSAN Capacity Disks**.
7. Complete the network interface settings:
   1. Enter the host name prefix, subdomain label, and domain name.
   2. Select the network interface to use:
    * If you want to order new public and private VLANs, click **Order New VLANs**.
    * If you want to reuse the existing public and private VLANs when they are available, click **Select Existing VLANs** and specify the VLANs and optionally the subnets.
    3. Specify whether to apply the FortiGate Physical Appliance 300 Series HA Pair to secure your cloud environment.  
8. In the **Order Summary** pane, verify the cluster configuration and the estimated cost.
   * To save the configuration as a template without placing an order, click **Save Configuration**.
   * To place the order, ensure that the account to be charged is correct, review and accept the terms, and then click **Provision**.

   **Note**: Only the {{site.data.keyword.baremetal_short}} are installed. You are responsible for installing and configuring various components after cluster deployment, such as VMware vCenter, VMware NSX, VMware vSAN.

## Results

If you saved the cluster configuration as a template, you get a console notification that the configuration is saved successfully, and then you can find the template in the **Cluster Configurations** list.

If you placed an order, the deployment of the cluster starts automatically, and you receive an email confirmation that the order is being processed. When the cluster is ready to use, you are notified by email.

**Note:** The vSphere clusters, unlike the vCenter Server and Cloud Foundation instances, are not displayed on the **Deployed Instances** page.

## Related links

* [Ordering vSphere clusters based on existing configurations](vs_orderingbasedonexistingconfig.html)
* [Scaling existing clusters](vs_scalingexistingclusters.html)
* [Scaling clusters created outside of the console](vs_orderingforclustersoutside.html)
