:original_name: vpcep_ug_0003.html

.. _vpcep_ug_0003:

Creating a User and Granting Permissions
========================================

Use `IAM <https://docs.otc.t-systems.com/identity-access-management/umn/service_overview/what_is_iam.html>`__ to implement fine-grained permissions control over your VPCEP resources. With IAM, you can:

-  Create IAM users for personnel based on your enterprise's organizational structure. Each IAM user has their own identity credentials for accessing VPCEP resources.
-  Grant users only the permissions required to perform a given task based on their job responsibilities.
-  Entrust an account or a cloud service to perform efficient O&M on your VPCEP resources.

If your account meets your permissions requirements, you can skip this section.

:ref:`Figure 1 <vpcep_ug_0003__en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719>` shows the process flow of granting permissions.

Prerequisites
-------------

Before granting permissions to user groups, learn about permissions (see :ref:`Permissions <vpcep_pd_0001>`) supported by VPCEP and choose policies or roles according to your requirements. To grant permissions for other services, learn about all `Permissions <https://docs.otc.t-systems.com/additional/permissions.html>`__ supported by IAM.

Process Flow
------------

.. _vpcep_ug_0003__en-us_topic_0173481716_en-us_topic_0172268189_fig12481104618719:

.. figure:: /_static/images/en-us_image_0000001089067433.png
   :alt: **Figure 1** Process of granting VPCEP permissions

   **Figure 1** Process of granting VPCEP permissions

#. `Create a user group and assign it permissions <https://docs.otc.t-systems.com/identity-access-management/umn/getting_started/creating_a_user_group_and_assigning_permissions.html>`__.

   On the IAM console, create a user group and assign the **VPCEndpoint Administrator** permissions to the group.

#. `Create an IAM user and add it to the created user group <https://docs.otc.t-systems.com/identity-access-management/umn/getting_started/creating_a_user_and_adding_the_user_to_a_user_group.html>`__.

#. `Log in as the IAM user <https://docs.otc.t-systems.com/identity-access-management/umn/getting_started/logging_in_as_a_user.html>`__ and verify permissions.

   In the authorized region, perform the following operations:

   -  Click **Service List**> **VPC Endpoint**. Then click **Create** **VPC Endpoint** in the upper right corner. If you can create a VPC endpoint, the **VPCEndpoint Administrator** policy is in effect.
   -  Choose another service from **Service List**. If a message appears indicating that you have insufficient permissions to access the service, the **VPCEndpoint Administrator** policy is in effect.
