:original_name: vpcep_03_0105.html

.. _vpcep_03_0105:

Managing Whitelist Records of a VPC Endpoint Service
====================================================

Scenarios
---------

Permission management controls the access of a VPC endpoint in one domain to a VPC endpoint service in another.

After a VPC endpoint service is created, you can add an authorized domain ID to or delete it from the whitelist of the endpoint service.

-  If the whitelist is empty, access from a VPC endpoint in another domain is not allowed.
-  If an authorized domain ID is already in the whitelist, you can use this domain to create a VPC endpoint for connecting to the VPC endpoint service.
-  If an authorized domain ID is not in the whitelist, you cannot use this domain to create a VPC endpoint for connecting to the VPC endpoint service.

This section describes how to add or delete a whitelist record for a VPC endpoint service.

Add a Whitelist Record
----------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.

6. On the displayed page, select the **Permission Management** tab and click **Add to Whitelist**.

7. Enter an authorized domain ID in the required format and click **OK**.


   .. figure:: /_static/images/en-us_image_0000001124314193.png
      :alt: **Figure 1** Add to Whitelist

      **Figure 1** Add to Whitelist

   .. note::

      -  Your domain is in the whitelist of your VPC endpoint service by default.

      -  The authorized domain ID is in the **iam:domain::domain_id** format.

         *domain_id* indicates the ID of the authorized domain, for example, **iam:domain::1564ec50ef2a47c791ea5536353ed4b9**

      -  Adding **\*** to the whitelist means that all users can access the VPC endpoint service.

Delete a Whitelist Record
-------------------------

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.

6. On the displayed page, select the **Permission Management** tab, locate the target domain ID, and click **Delete** in the **Operation** column.

   To delete multiple whitelist records, select all the target domain IDs and click **Delete** in the upper left corner.

7. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0289945877.png
