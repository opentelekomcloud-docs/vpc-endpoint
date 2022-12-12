:original_name: vpcep_02_0403.html

.. _vpcep_02_0403:

Step 2: Access OBS
==================

Scenarios
---------

This section describes how to access OBS using a VPN connection or a direct connection.

Prerequisites
-------------

Your local data center has been connected to your VPC using a VPN or Direct Connect connection.

-  The local subnet of your VPC that interconnects with your VPN connection contains the OBS CIDR block.

   For details about how to create a VPN connection, see `Creating a VPN <https://docs.otc.t-systems.com/en-us/usermanual/vpn/en-us_topic_0060118606.html>`__ in the *Virtual Private Network User Guide*.

-  The VPC subnet associated with the virtual gateway contains the OBS CIDR block.

   For details about how to enable Direct Connect, see `Getting Started <https://docs.otc.t-systems.com/en-us/usermanual/dc/en-us_topic_0032025289.html>`__ in the *Direct Connect User Guide*.

Procedure
---------

Configure an OBS route from the local data center to the VPN or Direct Connect gateway.

The CIDR block of the VPC endpoint for accessing OBS is a public CIDR block. To access OBS using a VPN connection or direct connection, ensure that traffic from your local data center to OBS is directed to the VPN gateway or Direct Connect gateway.

Configure a permanent route at your local data center and specify the Direct Connect or VPN gateway as the next hop for accessing OBS. The following is the example command for configuring such a route:

**route -p add** *Public IP address xxx.xxx.xxx.xxx*

.. note::

   -  *Public IP address* indicates the address for accessing OBS.
   -  *xxx.xxx.xxx.xxx* indicates the IP address of the Direct Connect or VPN gateway created at your local data center.
