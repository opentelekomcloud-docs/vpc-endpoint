:original_name: vpcep_03_0108.html

.. _vpcep_03_0108:

Managing Tags of a VPC Endpoint Service
=======================================

Scenarios
---------

After a VPC endpoint service is created, you can view its tags, or add, edit, or delete a tag.

A tag is a unique identifier of each VPC endpoint service, and it consists of a tag key and a tag value. You can add a maximum of 20 tags to each VPC endpoint service.

.. note::

   If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.

   For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.

Add a Tag
---------

Perform the following operations to add a tag for an existing VPC endpoint service:

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.

6. On the displayed page, select the **Tags** tab.

7. Click **Add Tag**.

8. In the displayed dialog box, enter a key and a value.

   :ref:`Table 1 <vpcep_03_0108__table183931759191417>` describes the required parameters.

   .. _vpcep_03_0108__table183931759191417:

   .. table:: **Table 1** Tag requirements for VPC endpoint services

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

9. Click **OK**.

Edit a Tag
----------

Perform the following operations to edit a tag of a VPC endpoint service:

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.
5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.
6. On the displayed page, select the **Tags** tab.
7. In the tag list, locate the target tag and click **Edit** in the **Operation** column.
8. Enter a new value.

   .. note::

      You can only edit tags that have values.

9. Click **OK**.

Delete a Tag
------------

Perform the following operations to delete a tag of a VPC endpoint service:

.. caution::

   Deleted tags cannot be recovered. Exercise caution when performing this operation.

#. Log in to the management console.
#. Click |image3| in the upper left corner and select the required region and project.

3. Choose **Service List** > **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.
5. In the VPC endpoint service list, locate the target VPC endpoint service and click its name.
6. On the displayed page, select the **Tags** tab.
7. In the tag list, locate the target tag and click **Delete** in the **Operation** column.
8. Click **Yes**.

.. |image1| image:: /_static/images/en-us_image_0289945877.png
.. |image2| image:: /_static/images/en-us_image_0289945877.png
.. |image3| image:: /_static/images/en-us_image_0289945877.png
