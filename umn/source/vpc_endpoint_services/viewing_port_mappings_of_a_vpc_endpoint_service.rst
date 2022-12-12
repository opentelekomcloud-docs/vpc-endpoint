:original_name: vpcep_03_0106.html

.. _vpcep_03_0106:

Viewing Port Mappings of a VPC Endpoint Service
===============================================

Scenarios
---------

After a VPC endpoint service is created, you can view the added port mappings.

A port mapping defines the protocol and ports used for communications between a VPC endpoint and a VPC endpoint service.

-  Protocol: A protocol both supported by the VPC endpoint and VPC endpoint service
-  Service Port: A service port is provided by the backend service bound to the endpoint service.
-  Terminal Port: A terminal port is provided by the VPC endpoint, allowing you to access the VPC endpoint service.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.

6. On the displayed page, select the **Port Mapping** tab.

   The port mapping configured for the VPC endpoint service is displayed.


   .. figure:: /_static/images/en-us_image_0000001124517799.png
      :alt: **Figure 1** Port Mapping

      **Figure 1** Port Mapping

.. |image1| image:: /_static/images/en-us_image_0289945877.png
