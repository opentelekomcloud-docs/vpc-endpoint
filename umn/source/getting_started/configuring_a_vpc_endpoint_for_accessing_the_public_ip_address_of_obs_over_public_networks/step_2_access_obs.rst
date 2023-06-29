:original_name: vpcep_02_0403.html

.. _vpcep_02_0403:

Step 2: Access OBS
==================

Scenarios
---------

This section describes how to access OBS using a VPN or Direct Connect connection.

Prerequisites
-------------

Your on-premises data center has been connected to your VPC using a VPN or Direct Connect connection.

-  The VPC subnet associated with the VPN gateway contains the OBS CIDR block.

   For details about how to create a VPN connection, see `Creating a VPN <https://docs.otc.t-systems.com/en-us/usermanual/vpn/en-us_topic_0060118606.html>`__ in the *Virtual Private Network User Guide*.

-  The VPC subnet associated with the Direct Connect gateway contains the OBS CIDR block.

   For details about how to enable Direct Connect, see `Getting Started <https://docs.otc.t-systems.com/direct-connect/umn/getting_started/index.html>`__ in the *Direct Connect User Guide*.

Procedure
---------

Configure an OBS route from the on-premises data center to the VPN or Direct Connect gateway.

The CIDR block of the VPC endpoint for accessing OBS is a public CIDR block. To access OBS over a VPN or Direct Connect connection, ensure that traffic from your on-premises data center to OBS is directed to the VPN gateway or Direct Connect gateway.

Configure a permanent route at your on-premises data center and specify the Direct Connect or VPN gateway as the next hop for accessing OBS. The following is the example command for configuring such a route:

.. code-block::

   route -p add Public IP address xxx.xxx.xxx.xxx

.. note::

   -  *Public IP address* indicates the address for accessing OBS.
   -  *xxx.xxx.xxx.xxx* indicates the IP address of the Direct Connect or VPN gateway created at your on-premises data center.
   -  The route command format varies depending on the OS. Use the route command format corresponding to the actual OS.
