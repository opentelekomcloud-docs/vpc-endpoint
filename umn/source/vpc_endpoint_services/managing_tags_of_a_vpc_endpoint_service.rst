:original_name: vpcep_03_0108.html

.. _vpcep_03_0108:

Managing Tags of a VPC Endpoint Service
=======================================

Scenarios
---------

After a VPC endpoint service is created, you can view its tags, or add, edit, or delete a tag.

Tags help identify VPC endpoint services. You can add up to 20 tags to each VPC endpoint service.

.. note::

   If a predefined tag has been created on TMS, you can directly select the corresponding tag key and value.

   For details about predefined tags, see `Predefined Tag Overview <https://docs.otc.t-systems.com/usermanual/tms/en-us_topic_0056266269.html>`__.

Add a Tag
---------

Perform the following operations to tag an existing VPC endpoint service:

#. Log in to the management console.
#. Click |image1| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.

5. In the VPC endpoint service list, locate the VPC endpoint service and click its name.

6. On the displayed page, select the **Tags** tab.

7. Click **Add Tag**.

8. In the displayed **Add Tag** dialog box, enter a key and a value.

   :ref:`Table 1 <vpcep_03_0108__table183931759191417>` describes the tag requirements.

   .. _vpcep_03_0108__table183931759191417:

   .. table:: **Table 1** Tag requirements for VPC endpoint services

      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Parameter                         | Requirement                                                                          |
      +===================================+======================================================================================+
      | Tag key                           | -  Cannot be left blank.                                                             |
      |                                   | -  Must be unique for each resource.                                                 |
      |                                   | -  Can contain a maximum of 36 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+
      | Tag value                         | -  Can contain a maximum of 43 characters.                                           |
      |                                   | -  Can contain only digits, letters, hyphens (-), underscores (_), and at signs (@). |
      +-----------------------------------+--------------------------------------------------------------------------------------+

9. Click **OK**.

Edit a Tag
----------

Perform the following operations to edit a tag of a VPC endpoint service:

#. Log in to the management console.
#. Click |image2| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.
5. In the VPC endpoint service list, locate the VPC endpoint service and click its name.
6. On the displayed page, select the **Tags** tab.
7. In the tag list, locate the tag and click **Edit** in the **Operation** column.
8. Enter a new value.

   .. note::

      You can only edit tag values.

9. Click **OK**.

Delete a Tag
------------

Perform the following operations to delete a tag of a VPC endpoint service:

.. caution::

   Deleted tags cannot be recovered. Exercise caution when performing this operation.

#. Log in to the management console.
#. Click |image3| in the upper left corner and select the required region and project.

3. Click **Service List** and choose **Networking** > **VPC Endpoint**.

4. In the navigation pane on the left, choose **VPC Endpoint** > **VPC Endpoint Services**.
5. In the VPC endpoint service list, locate the VPC endpoint service and click its name.
6. On the displayed page, select the **Tags** tab.
7. In the tag list, locate the tag and click **Delete** in the **Operation** column.
8. In the displayed dialog box, click **OK**.

.. |image1| image:: /_static/images/en-us_image_0000001979891813.png
.. |image2| image:: /_static/images/en-us_image_0000001979891813.png
.. |image3| image:: /_static/images/en-us_image_0000001979891813.png
