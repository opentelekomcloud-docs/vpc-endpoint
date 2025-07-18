:original_name: vpcep_01_0011.html

.. _vpcep_01_0011:

Region and AZ
=============

Concept
-------

A region and availability zone (AZ) identify the location of a data center. You can create resources in a specific region and AZ.

-  A region is a physical data center, which is completely isolated to improve fault tolerance and stability. The region that is selected during resource creation cannot be changed after the resource is created.
-  An AZ is a physical location where resources use independent power supplies and networks. A region contains one or more AZs that are physically isolated but interconnected through internal networks. Because AZs are isolated from each other, any fault that occurs in one AZ will not affect others.

:ref:`Figure 1 <vpcep_01_0011__en-us_topic_0184026189_fig8747114281212>` shows the relationship between regions and AZs.

.. _vpcep_01_0011__en-us_topic_0184026189_fig8747114281212:

.. figure:: /_static/images/en-us_image_0184026531.png
   :alt: **Figure 1** Regions and AZs

   **Figure 1** Regions and AZs

Selecting a Region
------------------

You are advised to select a region close to you or your target users. This helps ensure low access latency.

Selecting an AZ
---------------

When deploying resources, consider your applications' requirements on disaster recovery (DR) and network latency.

-  For high DR capability, deploy resources in different AZs within the same region.
-  For lower network latency, deploy resources in the same AZ.

Regions and Endpoints
---------------------

Before you use an API to call resources, specify its region and endpoint. For more details, see `Regions and Endpoints <https://docs.otc.t-systems.com/regions-and-endpoints/index.html>`__.
