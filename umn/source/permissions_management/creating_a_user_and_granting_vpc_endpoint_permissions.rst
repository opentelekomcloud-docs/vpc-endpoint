:original_name: vpcep_ug_0003.html

.. _vpcep_ug_0003:

Creating a User and Granting VPC Endpoint Permissions
=====================================================

Use `IAM <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__ to implement fine-grained permissions control over your VPC Endpoint resources. With IAM, you can:

-  Create IAM users for employees based on your enterprise's organizational structure. Each IAM user has their own security credentials for accessing VPC Endpoint resources.
-  Grant only the permissions required for users to perform a specific task.
-  Entrust an account or a cloud service to perform efficient O&M on your VPC Endpoint resources.

If your account does not need individual IAM users, skip this section.

This section describes the process flow for granting permissions (see :ref:`Figure 1 <vpcep_ug_0003__en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719>`).

Prerequisites
-------------

You must learn about permissions (see :ref:`Permissions <vpcep_pd_0001>`) supported by VPC Endpoint and choose policies or roles according to your requirements. To grant permissions for other services, learn about all `Permissions <https://docs.otc.t-systems.com/permissions/index.html>`__ supported by IAM.

Process Flow
------------

.. _vpcep_ug_0003__en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719:

.. figure:: /_static/images/en-us_image_0000001949612456.png
   :alt: **Figure 1** Process for granting VPC Endpoint permissions

   **Figure 1** Process for granting VPC Endpoint permissions

#. .. _vpcep_ug_0003__en-us_topic_0173481716_en-us_topic_0172268189_li10269636890:

   `Create a user group and assign it permissions <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0030.html>`__.

   On the IAM console, create a user group and attach the **VPCEndpoint Administrator** policy to the group.

#. `Create an IAM user and add it to the created user group <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0031.html>`__.

   Create an IAM user and add it to the user group created in :ref:`1 <vpcep_ug_0003__en-us_topic_0173481716_en-us_topic_0172268189_li10269636890>`.

#. `Log in as the IAM user <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0032.html>`__ and verify permissions.

   In the authorized region, perform the following operations:

   -  On the **Service List** page, choose **VPC Endpoint**. Click **Create** **VPC Endpoint** in the upper right corner. If you can create a VPC endpoint, the **VPCEndpoint Administrator** policy has already taken effect.
   -  Choose another service from **Service List**. If a message appears indicating that you have insufficient permissions to access the service, the **VPCEndpoint Administrator** policy has already taken effect.
