:original_name: vpcep_02_0301.html

.. _vpcep_02_0301:

Overview
========

Scenarios
---------

If you want to access a cloud service like OBS from an IDC, you can connect the IDC to your VPC using a VPN connection or a direct connection and then connect your VPC to a cloud service using a VPC endpoint.

This section describes how to configure a VPC endpoint to access OBS using its private address from an IDC.

.. _vpcep_02_0301__fig1589611845912:

.. figure:: /_static/images/en-us_image_0298583614.png
   :alt: **Figure 1** Accessing OBS using its private address from an IDC

   **Figure 1** Accessing OBS using its private address from an IDC

:ref:`Figure 1 <vpcep_02_0301__fig1589611845912>` shows the process of connecting an IDC to a VPC over VPN or Direct Connect to access DNS and OBS using two VPC endpoints, respectively.

A VPC endpoint comes with a VPC endpoint service. Before you create a VPC endpoint, ensure that the VPC endpoint service that you want to access is available.

The following VPC endpoint services are required:

-  VPC endpoint service for DNS: resolves the OBS domain name at the IDC.

   eu-de: **com.t-systems.otc.eu-de.dns**

-  VPC endpoint service for OBS: provides the OBS service for the IDC.

   eu-de: **com.t-systems.otc.eu-de.obs**

Configuration Process
---------------------

:ref:`Figure 2 <vpcep_02_0301__fig11842192183914>` shows the process for configuring a VPC endpoint to access OBS using its private address from an IDC.

.. _vpcep_02_0301__fig11842192183914:

.. figure:: /_static/images/en-us_image_0298561817.png
   :alt: **Figure 2** Configuration flowchart

   **Figure 2** Configuration flowchart
