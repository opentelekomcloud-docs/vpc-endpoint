:original_name: vpcep_02_02034.html

.. _vpcep_02_02034:

Step 2: Add a Whitelist Record
==============================

Scenarios
---------

Permission management controls the access of a VPC endpoint in one domain to a VPC endpoint service in another.

After a VPC endpoint service is created, you can add an authorized domain ID to or delete it from the whitelist of the endpoint service.

The following operations describe how to obtain your own domain ID and add it to the whitelist of an existing VPC endpoint service in another domain.

Prerequisites
-------------

The required VPC endpoint service already exists.

Obtain the ID of Your Own Domain
--------------------------------

#. Log in to the management console.

#. Click **My Credentials** under the domain.


   .. figure:: /_static/images/en-us_image_0289945758.png
      :alt: **Figure 1** My Credentials

      **Figure 1** My Credentials

   The **My Credentials** page is displayed. You can view and record the Domain ID.


   .. figure:: /_static/images/en-us_image_0289945818.png
      :alt: **Figure 2** Domain ID

      **Figure 2** Domain ID

Add an Authorized Domain ID to the Whitelist of a VPC Endpoint Service
----------------------------------------------------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.

6. On the displayed page, select the **Permission Management** tab and click **Add to Whitelist**.

7. Enter an authorized domain ID in the required format and click **OK**.


   .. figure:: /_static/images/en-us_image_0000001124314193.png
      :alt: **Figure 3** Add to Whitelist

      **Figure 3** Add to Whitelist

   .. note::

      -  Your domain is in the whitelist of your VPC endpoint service by default.

      -  The authorized domain ID is in the **iam:domain::domain_id** format.

         *domain_id* indicates the ID of the authorized domain, for example, **iam:domain::1564ec50ef2a47c791ea5536353ed4b9**

      -  Adding **\*** to the whitelist means that all users can access the VPC endpoint service.

8. Click **OK**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
