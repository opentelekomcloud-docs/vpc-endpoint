:original_name: vpcep_02_0304.html

.. _vpcep_02_0304:

Step 3: Access OBS
==================

Scenarios
---------

This section describes how to access OBS using a VPN or Direct Connect connection.

Prerequisites
-------------

Your on-premises data center has been connected to your VPC using a VPN or Direct Connect connection.

-  The VPC subnet that needs to communicate with the on-premises data center over the VPN connection contains the OBS CIDR block 100.125.0.0/16.

   For details about how to create a VPN connection, see `Creating a VPN <https://docs.otc.t-systems.com/en-us/usermanual/vpn/en-us_topic_0060118606.html>`__ in the *Virtual Private Network User Guide*.

-  The VPC subnet that needs to communicate with the on-premises data center over the Direct Connect gateway contains the OBS CIDR block 100.125.0.0/16.

   For details about how to enable Direct Connect, see `Getting Started <https://docs.otc.t-systems.com/direct-connect/umn/getting_started/index.html>`__ in the *Direct Connect User Guide*.

Procedure
---------

#. .. _vpcep_02_0304__li146041853163516:

   In the VPC endpoint list, locate the target VPC endpoint and click the ID of the endpoint to view its details.


   .. figure:: /_static/images/en-us_image_0289945827.png
      :alt: **Figure 1** Summary of the VPC endpoint

      **Figure 1** Summary of the VPC endpoint

#. Add DNS records on the DNS server at your on-premises data center to forward requests for resolving OBS domain names to the VPC endpoint for accessing DNS.

   The methods of configuring DNS forwarding rules vary depending on OSs. For details, see the DNS software operation guides.

   This step uses Bind, a common DNS software, as an example to configure forwarding rules in the UNIX.

   In file **/etc/named.conf**, add the DNS forwarder configuration and set **forwarders** to the private IP address of the VPC endpoint for accessing DNS.

   .. code-block::

      options {
      forward only;
      forwarders{ xx.xx.xx.xx;};
      };

   .. note::

      -  If no DNS server is available at your on-premises data center, add the private IP address of the VPC endpoint in file **/etc/resolv.conf**.
      -  *xx.xx.xx.xx* is the VPC endpoint IP address obtained in :ref:`1 <vpcep_02_0304__li146041853163516>`.

#. Configure a DNS route from your on-premises data center to the VPN gateway or Direct Connect gateway.

   To access DNS over a VPN or Direct Connect connection, ensure that traffic from your on-premises data center to DNS is directed to the VPN gateway or Direct Connect gateway.

   Configure a permanent route at your on-premises data center and specify the IP address of the Direct Connect or VPN gateway as the next hop for accessing DNS. The following is the example command for configuring such a route:

   .. code-block::

      route -p add xx.xx.xx.xx mask 255.255.255.255 xxx.xxx.xxx.xxx

   .. note::

      -  *xx.xx.xx.xx* is the VPC endpoint IP address obtained in :ref:`1 <vpcep_02_0304__li146041853163516>`.
      -  *xxx.xxx.xxx.xxx* indicates the IP address of the Direct Connect or VPN gateway created at your on-premises data center.
      -  The route command format varies depending on the OS. Use the route command format corresponding to the actual OS.

#. Configure an OBS route from the on-premises data center to the VPN or Direct Connect gateway.

   The CIDR block of the VPC endpoint for accessing OBS is 100.125.0.0/16. To access OBS over a VPN or Direct Connect connection, ensure that traffic from your on-premises data center to OBS is directed to the VPN gateway or Direct Connect gateway.

   Configure a permanent route at your on-premises data center and specify the Direct Connect or VPN gateway as the next hop for accessing OBS. The following is the example command for configuring such a route:

   .. code-block::

      route -p add 100.125.0.0 mask 255.255.0.0 xxx.xxx.xxx.xxx

   .. note::

      -  *xxx.xxx.xxx.xxx* indicates the IP address of the Direct Connect or VPN gateway created at your on-premises data center.
      -  The route command format varies depending on the OS. Use the route command format corresponding to the actual OS.

#. At the on-premises data center, run the following command to verify the connectivity with OBS:

   .. code-block::

      telnet bucket.endpoint

   In the command:

   -  *bucket*: indicates the bucket name.
   -  *endpoint*: indicates the OBS endpoint.

   Example: **telnet** **bucket.obs.eu-de.otc.t-systems.com**

   .. note::

      Obtain OBS endpoint information at `Regions and Endpoints <https://docs.otc.t-systems.com/en-us/endpoint/index.html>`__.
