---
type: rule
title: Do you know when to use Geo Redundant Storage?
uri: do-you-know-when-to-use-geo-redundant-storage
authors:
  - title: Adam Stephensen
    url: https://ssw.com.au/people/adam-stephensen
related: []
redirects: []
created: 2015-02-10T18:34:05.000Z
archivedreason: null
guid: 812032fc-e91b-4fa1-8aa3-7a10fc3d3cc1
---
Data in Azure Storage accounts is protected by replication. Deciding how far to replicate it is a balance between safety and cost.

![Figure: It is important to balance safety and pricing when choosing the right replication strategy for Azure Storage Accounts](azure-graphic.jpg)

<!--endintro-->

**Locally redundant storage (LRS)**

* Maintains three copies of your data.
* Is replicated three times within a single facility in a single region.
* Protects your data from normal hardware failures, but not from the failure of a single facility.
* Less expensive than GRS
* Use when:

  * Data is of low importance – e.g. for test websites, or testing virtual machines
  * Data can be easily reconstructed
  * Data is non-critical
  * Data governance requirements restrict data to a single region

**Geo-redundant storage (GRS).**

* The default when you create it storage accounts.
* Maintains six copies of your data.
* Data is replicated three times within the primary region, and is also replicated three times in a secondary region hundreds of miles away from the primary region
* In the event of a failure at the primary region, Azure Storage will failover to the secondary region.
* Ensures that your data is durable in two separate regions.
* Use when:

  * Data cannot be recovered if lost

**Read access geo-redundant storage (RA-GRS).**  

* Replicates your data to a secondary geographic location (same as GRS)
* Provides read access to your data in the secondary location
* Allows you to access your data from either the primary or the secondary location, in the event that one location becomes unavailable.
* Use when:

  * Data is critical, and access is required to both the primary and the secondary regions

More reading

* [Azure Storage Redundancy Option](https://msdn.microsoft.com/en-us/library/azure/dn727290.aspx)