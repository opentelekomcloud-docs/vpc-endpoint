:original_name: vpcep_03_0106.html

.. _vpcep_03_0106:

Viewing Port Mappings of a VPC Endpoint Service
===============================================

Scenarios
---------

After a VPC endpoint service is created, you can view the added port mappings.

A port mapping defines the protocol and ports used for communications between a VPC endpoint and a VPC endpoint service.

-  **Protocol**: a protocol both supported by the VPC endpoint and VPC endpoint service
-  **Service Port**: provided by the backend resource bound to the VPC endpoint service.
-  **Terminal Port**: provided by the VPC endpoint, allowing you to access the VPC endpoint service.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the VPC endpoint service and click its name.

6. On the displayed page, select the **Port Mapping** tab.

   The port mappings configured for the VPC endpoint service are displayed.


   .. figure:: /_static/images/en-us_image_0000002184495069.png
      :alt: **Figure 1** Port Mapping

      **Figure 1** Port Mapping

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
