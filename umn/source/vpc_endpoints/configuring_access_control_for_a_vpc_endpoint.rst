:original_name: vpcep_03_0205.html

.. _vpcep_03_0205:

Configuring Access Control for a VPC Endpoint
=============================================

Scenarios
---------

To control IP addresses and CIDR blocks that can access a VPC endpoint, configure a whitelist. You can add or delete a whitelist record, or disable access control if you no longer need it.

For details about how to configure access control and whitelist when you are creating a VPC endpoint, see :ref:`Creating a VPC Endpoint <en-us_topic_0131645189>`.

This section describes how to enable and configure access control after a VPC endpoint is created.

Constraints
-----------

-  **Access Control** is only available for VPC endpoints for connecting to interface VPC endpoint services.
-  If **Access Control** is disabled, any IP address can access the VPC endpoint.
-  A maximum of 20 whitelist records can be added.

Enable Access Control and Add a Whitelist Record
------------------------------------------------

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the VPC endpoint list, locate the VPC endpoint and click its ID.

5. On the displayed page, click the **Access Control** tab.

6. On the **Access Control** tab, click **Add to Whitelist**.


   .. figure:: /_static/images/en-us_image_0000002184649877.png
      :alt: **Figure 1** Adding a whitelist record for the VPC endpoint

      **Figure 1** Adding a whitelist record for the VPC endpoint

7. Enter the authorized IP addresses or CIDR blocks.

8. Click **OK**.

Delete a Whitelist Record
-------------------------

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the VPC endpoint list, locate the VPC endpoint and click its ID.

5. Select the **Access Control** tab.

6. In the whitelist, locate the IP address or CIDR block and click **Delete** in the **Operation** column.

   To delete whitelist records, select all the target IP addresses or CIDR blocks and click **Delete** in the upper left corner.

7. In the displayed **Delete from Whitelist** dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
.. |image2| image:: /_static/images/en-us_image_0000001979891813.png
