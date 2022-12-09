:original_name: vpcep_02_0304.html

.. _vpcep_02_0304:

Step 3: Access OBS
==================

Scenarios
---------

This section describes how to access OBS using a VPN connection or a direct connection.

Prerequisites
-------------

Your local data center has been connected to your VPC using a VPN or Direct Connect connection.

-  The local subnet of the VPC that interconnects with your VPN contains the OBS CIDR block 100.125.0.0/16.

   For details about how to create a VPN connection, see `Creating a VPN <https://docs.otc.t-systems.com/en-us/usermanual/vpn/en-us_topic_0060118606.html>`__ in the *Virtual Private Network User Guide*.

-  The CIDR block of the virtual gateway associated with your direct connection contains the OBS CIDR block 100.125.0.0/16.

   For details about how to enable Direct Connect, see `Getting Started <https://docs.otc.t-systems.com/en-us/usermanual/dc/en-us_topic_0032025289.html>`__ in the *Direct Connect User Guide*.

Procedure
---------

#. .. _vpcep_02_0304__li146041853163516:

   In the VPC endpoint list, locate the target VPC endpoint and click the ID of the endpoint to view its details.


   .. figure:: /_static/images/en-us_image_0289945827.png
      :alt: **Figure 1** Summary of the VPC endpoint

      **Figure 1** Summary of the VPC endpoint

#. Add DNS records on the DNS server at your local data center to forward requests for resolving OBS domain names to the VPC endpoint for accessing DNS.

   The methods of configuring DNS forwarding rules vary depending on operating systems. For details, see the DNS software operation documents.

   This step uses the common DNS software Bind as an example to configure forwarding rules in the UNIX operating system as follows:

   In file **/etc/named.conf**, add the DNS forwarder configuration and set **forwarders** to the private IP address of the VPC endpoint for accessing DNS.

   **options {**

   **forward only;**

   **forwarders{** *xx.xx.xx.xx*\ **;};**

   **};**

   .. note::

      -  If no DNS server is available at your local data center, add the private IP address of the VPC endpoint in file **/etc/resolv.conf**.
      -  *xx.xx.xx.xx* is the private IP address obtained in step :ref:`1 <vpcep_02_0304__li146041853163516>`.

#. Configure a DNS route from your local data center to the VPN gateway or Direct Connect gateway.

   *xx.xx.xx.xx* indicates the private IP address of the VPC endpoint. To access DNS using a VPN connection or a direct connection, you need to ensure that traffic from your local data center to DNS is directed to the VPN gateway or Direct Connect gateway.

   Configure a permanent route at your local data center and specify the IP address of the Direct Connect or VPN gateway as the next hop for accessing DNS.

   **route -p add** *xx.xx.xx.xx* **mask 255.255.255.255** *xxx.xxx.xxx.xxx*

   .. note::

      -  *xx.xx.xx.xx* is the private IP address obtained in step :ref:`1 <vpcep_02_0304__li146041853163516>`.
      -  *xxx.xxx.xxx.xxx* indicates the IP address of the Direct Connect or VPN gateway created at your local data center.

#. Configure an OBS route from the local data center to the VPN or Direct Connect gateway.

   The CIDR block of the VPC endpoint for accessing OBS is 100.125.0.0/16. To access OBS using a VPN connection or direct connection, you need to ensure that traffic from your local data center to OBS is directed to the VPN gateway or Direct Connect gateway.

   Configure a permanent route at your local data center and specify the Direct Connect or VPN gateway as the next hop for accessing OBS.

   **route -p add 100.125.0.0 mask 255.255.0.0** *xxx.xxx.xxx.xxx*

   .. note::

      *xxx.xxx.xxx.xxx* indicates the IP address of the Direct Connect or VPN gateway created at your local data center.

#. At the local data center, run the following command to verify the connectivity with OBS:

   **telnet** *bucket.endpoint*

   In the command:

   -  *bucket*: indicates the bucket name.
   -  *endpoint*: indicates the endpoint information about OBS.

   Example: **telnet** **bucket.obs.eu-de.otc.t-systems.com**

   .. note::

      Obtain OBS endpoint information at `Regions and Endpoints <https://docs.otc.t-systems.com/en-us/endpoint/index.html>`__.
