:original_name: vpcep_02_0401.html

.. _vpcep_02_0401:

Overview
========

Scenarios
---------

If you want to access OBS using its public address from an IDC, you can use a VPC endpoint to connect to the VPC endpoint service configured for OBS.

This section describes how to create such a VPC endpoint to access OBS.

.. note::

   This scenario is supported only in region eu-nl.

.. _vpcep_02_0401__fig1589611845912:

.. figure:: /_static/images/en-us_image_0298570037.png
   :alt: **Figure 1** Accessing OBS using its public address from an IDC

   **Figure 1** Accessing OBS using its public address from an IDC

:ref:`Figure 1 <vpcep_02_0401__fig1589611845912>` shows the process of connecting an IDC to a VPC over VPN or Direct Connect to access OBS using a VPC endpoint created in the VPC.

A VPC endpoint comes with a VPC endpoint service. Before you create a VPC endpoint, ensure that the VPC endpoint service that you want to access is available.

The following VPC endpoint services are required:

eu-nl: **com.t-systems.otc.eu-nl.obs-internet**

Configuration Process
---------------------

:ref:`Figure 2 <vpcep_02_0401__fig17254219184910>` shows the process for configuring a VPC endpoint to access OBS using its public address from an IDC.

.. _vpcep_02_0401__fig17254219184910:

.. figure:: /_static/images/en-us_image_0298571864.png
   :alt: **Figure 2** Configuration flowchart

   **Figure 2** Configuration flowchart
