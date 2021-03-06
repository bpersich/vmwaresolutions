---

copyright:

  years:  2016, 2018

lastupdated: "2018-05-04"

---

# Requesting managed services for Zerto on IBM Cloud

The Zerto on {{site.data.keyword.cloud}} service provides replication and disaster recovery capabilities, which can be integrated into the deployment offerings to protect and recover data in your VMware virtual environment on {{site.data.keyword.cloud_notm}}.

When you request managed services for Zerto on {{site.data.keyword.cloud_notm}}, a fully managed disaster recovery (DR) environment can be deployed using both Zerto DR software and IBM Resiliency Services.

The following models for managed services for Zerto on {{site.data.keyword.cloud_notm}} are available.

## IBM Orchestrated Managed Services for Zerto

This model is suitable if you are using the Zerto on {{site.data.keyword.cloud_notm}} offering.

In this model, the {{site.data.keyword.cloud_notm}} Resiliency Orchestration service is provisioned for Zerto on {{site.data.keyword.cloud_notm}}. This model allows for continuous protection of virtual machines, operating systems, and data on the {{site.data.keyword.cloud_notm}}, with uninterrupted DR testing, RTO/RPO (Recovery Time Objective/Recovery Point Objective) visibility, fail-over and fail-back capability.

All functions are managed via the {{site.data.keyword.cloud_notm}} Resiliency Orchestration dashboard by IBM Resiliency Services Global Command Center.

For more information, see [IBM Resiliency Orchestration](https://www.ibm.com/us-en/marketplace/disaster-recovery-orchestration).

## IBM Managed Services for Zerto (without Orchestration)

In this model, a fully managed DR solution is provisioned for Zerto on {{site.data.keyword.cloud_notm}}. This model is suitable if you want a managed service for Zerto Virtual Replication only, without the {{site.data.keyword.cloud_notm}} Resiliency Orchestration service on the {{site.data.keyword.cloud_notm}}.

For more information, see [IBM Resiliency Disaster Recovery as a Service](https://www.ibm.com/us-en/marketplace/disaster-recovery-as-a-service#product-header-top).

## Procedure

1. From the {{site.data.keyword.vmwaresolutions_short}} console, click **Getting Started** from the left navigation pane.
2. Scroll down the page and, under **Order additional managed services**, click the **Managed Services for Zerto on IBM Cloud** card.
3. On the **Order Managed Services for Zerto on IBM Cloud** page, review the description and technical specifications for Zerto on {{site.data.keyword.cloud_notm}} as a managed service and click **Create**.
4. Specify the configuration settings according to your requirements or accept the default values.
5. Click either **vCenter Server** or **Cloud Foundation** to add the service to one of your instances.
6. To add the service while you order a new instance, click **Add to New Instance** and continue with ordering a new [vCenter Server](../vcenter/vc_orderinginstance.html), [vCenter Server with Hybridity](../vcenter/vc_hybrid_orderinginstance.html), or [Cloud Foundation](../sddc/sd_orderinginstance.html) instance.
7. To add the service to an existing instance, click **Add to Deployed Instance** and select the instance that you want from the list, then confirm that you want to proceed with the order by clicking **Provision**.

## Related links

* [Ordering and removing services for vCenter Server instances](../vcenter/vc_addingremovingservices.html)
* [Ordering and removing services for Cloud Foundation instances](../sddc/sd_addingremovingservices.html)
* [Contacting IBM Support](../vmonic/trbl_support.html)
