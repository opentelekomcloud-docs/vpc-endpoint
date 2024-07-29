:original_name: vpcep_02_0301.html

.. _vpcep_02_0301:

Overview
========

Scenarios
---------

If you want to access a cloud service like OBS from an on-premises data center, you can connect the on-premises data center to your VPC using a VPN connection or a Direct Connect connection, and then use a VPC endpoint to access the cloud service from your VPC.

This section describes how to use a VPC endpoint to access OBS (private address) from an on-premises data center.

.. _vpcep_02_0301__fig1589611845912:

.. figure:: /_static/images/en-us_image_0000001980011633.png
   :alt: **Figure 1** Accessing OBS (private address) from an on-premises data center

   **Figure 1** Accessing OBS (private address) from an on-premises data center

:ref:`Figure 1 <vpcep_02_0301__fig1589611845912>` shows the process of connecting the on-premises data center to a VPC over VPN or Direct Connect, and then using two VPC endpoints to enable the on-premises data center to access DNS and OBS, respectively.

A VPC endpoint comes with a VPC endpoint service. Before you create a VPC endpoint, ensure that the VPC endpoint service that you want to access is available.

The following VPC endpoint services are required:

-  VPC endpoint service for DNS: resolves the OBS domain name at the on-premises data center.

   eu-de: **com.t-systems.otc.eu-de.dns**

-  VPC endpoint service for OBS: provides the OBS service for the on-premises data center.

   eu-de: **com.t-systems.otc.eu-de.obs**

Configuration Process
---------------------

:ref:`Figure 2 <vpcep_02_0301__fig11842192183914>` shows the process for configuring a VPC endpoint to access OBS (private address) from the on-premises data center.

.. _vpcep_02_0301__fig11842192183914:

.. figure:: /_static/images/en-us_image_0000001979891761.png
   :alt: **Figure 2** Configuration flowchart

   **Figure 2** Configuration flowchart
