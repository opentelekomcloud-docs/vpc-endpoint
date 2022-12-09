:original_name: vpcep_03_0104.html

.. _vpcep_03_0104:

Managing Connections of a VPC Endpoint Service
==============================================

Scenarios
---------

To connect a VPC endpoint to a VPC endpoint service that has connection approval enabled, obtain the approval from the owner of the endpoint service.

This section describes how to accept or reject connection of a VPC endpoint.

Prerequisites
-------------

There is a VPC endpoint available for connecting to the target VPC endpoint service.

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.

6. Select the **Connection Management** tab.


   .. figure:: /_static/images/en-us_image_0000001124399267.png
      :alt: **Figure 1** Connection Management

      **Figure 1** Connection Management

7. Accept or reject connection of a VPC endpoint in the list based on service requirements.

   -  If you click **Accept**, the VPC endpoint can connect to the VPC endpoint service.
   -  If you click **Reject**, the VPC endpoint cannot connect to the VPC endpoint service.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
