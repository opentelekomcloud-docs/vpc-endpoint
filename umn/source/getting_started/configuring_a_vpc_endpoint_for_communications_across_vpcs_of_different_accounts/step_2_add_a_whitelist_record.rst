:original_name: vpcep_02_02034.html

.. _vpcep_02_02034:

Step 2: Add a Whitelist Record
==============================

Scenarios
---------

Permission management controls the access of a VPC endpoint in one account to a VPC endpoint service in another.

After a VPC endpoint service is created, you can add or delete an authorized account ID to and from the whitelist of the VPC endpoint service.

The following operations describe how to obtain your account ID and add it to the whitelist of another user's VPC endpoint services.

Prerequisites
-------------

The required VPC endpoint service is available.

Obtain the ID of Your Own Account
---------------------------------

#. Log in to the management console.

#. Click **My Credentials** under the account.

   .. _vpcep_02_02034__fig1194755744:

   .. figure:: /_static/images/en-us_image_0000002000196417.png
      :alt: **Figure 1** My Credentials

      **Figure 1** My Credentials

   The **My Credentials** page is displayed. You can view and record the account ID.

   .. _vpcep_02_02034__fig14537232717:

   .. figure:: /_static/images/en-us_image_0000002000378297.png
      :alt: **Figure 2** Account ID

      **Figure 2** Account ID

.. _vpcep_02_02034__section19390104303219:

Add Account IDs to Be Authorized to the Whitelist of a VPC Endpoint Service
---------------------------------------------------------------------------

#. Click |image1| in the upper left corner and select the required region and project.

2. Click **Service List** and choose **Networking** > **VPC Endpoint**.

3. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

4. In the VPC endpoint service list, locate the VPC endpoint service and click its name.

5. On the displayed page, select the **Permission Management** tab and click **Add to Whitelist**.

6. Enter an authorized account ID in the required format and click **OK**.


   .. figure:: /_static/images/en-us_image_0000001980011797.png
      :alt: **Figure 3** Add to Whitelist

      **Figure 3** Add to Whitelist

   .. note::

      -  Your account is in the whitelist of your VPC endpoint service by default.

      -  The authorized account ID is in the **iam:domain::domain_id** format.

         *domain_id* indicates the ID of the authorized account, for example, **iam:domain::1564ec50ef2a47c791ea5536353ed4b9**

      -  Adding **\*** to the whitelist means that all users can access the VPC endpoint service.

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
