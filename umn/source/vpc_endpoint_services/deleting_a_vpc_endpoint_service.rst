:original_name: vpcep_03_0103.html

.. _vpcep_03_0103:

Deleting a VPC Endpoint Service
===============================

Scenarios
---------

This section describes how to delete a VPC endpoint service.

.. note::

   Deleted VPC endpoint services cannot be recovered. Exercise caution when performing this operation.

Constraints
-----------

-  The VPC endpoint services configured from your private services can be deleted, but those configured by the system cannot.

-  Any VPC endpoint service that has VPC endpoints in **Accepted** or **Creating** state cannot be deleted.

   For statuses of a VPC endpoint, see :ref:`What Statuses Are Available for a VPC Endpoint Service and VPC Endpoint? <vpcep_04_0005>`

Procedure
---------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click **Delete** in the **Operation** column.


   .. figure:: /_static/images/en-us_image_0000001124397561.png
      :alt: **Figure 1** Delete VPC Endpoint Service

      **Figure 1** Delete VPC Endpoint Service

6. In the displayed **Delete VPC Endpoint Service** dialog box, click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
