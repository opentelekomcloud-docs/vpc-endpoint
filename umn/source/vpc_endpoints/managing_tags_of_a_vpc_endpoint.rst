:original_name: vpcep_03_0206.html

.. _vpcep_03_0206:

Managing Tags of a VPC Endpoint
===============================

Scenarios
---------

After a VPC endpoint is created, you can view its tags, or add, edit, or delete a tag.

Each VPC endpoint has a unique tag, which consists of a tag key and a tag value. You can add a maximum of 20 tags to each VPC endpoint.

.. note::

   If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.

   For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.

Add a Tag
---------

Perform the following operations to add a tag for an existing VPC endpoint:

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the VPC endpoint list, locate the target VPC endpoint and click its ID.

5. On the displayed page, select the **Tags** tab.

6. Click **Add Tag**.

7. In the displayed dialog box, enter a key and a value.

   :ref:`Table 1 <vpcep_03_0206__table183931759191417>` describes the required parameters.

   .. _vpcep_03_0206__table183931759191417:

   .. table:: **Table 1** Tag requirements for VPC endpoints

      +-----------------------------------+------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                            |
      +===================================+========================================================================+
      | Tag key                           | -  Cannot be left blank.                                               |
      |                                   | -  Must be unique for each resource.                                   |
      |                                   | -  Can contain a maximum of 36 Unicode characters.                     |
      |                                   | -  Can contain only letters, digits, hyphens (-), and underscores (_). |
      +-----------------------------------+------------------------------------------------------------------------+
      | Tag value                         | -  Cannot be left blank.                                               |
      |                                   | -  Can contain a maximum of 43 Unicode characters.                     |
      |                                   | -  Can contain only letters, digits, hyphens (-), and underscores (_). |
      +-----------------------------------+------------------------------------------------------------------------+

8. Click **OK**.

Edit a Tag
----------

Perform the following operations to edit a tag of a VPC endpoint:

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the VPC endpoint list, locate the target VPC endpoint and click its ID.

5. On the displayed page, select the **Tags** tab.
6. In the tag list, locate the target tag and click **Edit** in the **Operation** column.
7. Enter a new value.

   .. note::

      You can only edit tags that have values.

8. Click **OK**.

Delete a Tag
------------

Perform the following operations to delete a tag of a VPC endpoint:

.. caution::

   Deleted tags cannot be recovered. Exercise caution when performing this operation.

#. Log in to the management console.
#. Click |image3| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the VPC endpoint list, locate the target VPC endpoint and click its ID.

5. On the displayed page, select the **Tags** tab.

6. In the tag list, locate the target tag and click **Delete** in the **Operation** column.
7. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0289945877.png
.. |image3| image:: /_static/images/en-us_image_0289945877.png
