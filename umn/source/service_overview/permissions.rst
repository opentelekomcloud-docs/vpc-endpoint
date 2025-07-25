:original_name: vpcep_pd_0001.html

.. _vpcep_pd_0001:

Permissions
===========

If you need to assign different permissions to employees in your enterprise to access your VPC Endpoint resources, you can use Identity and Access Management (IAM) to manage fine-grained permissions. IAM provides identity authentication, permissions management, and access control, helping you to securely access your cloud resources.

With IAM, you can use your account to create IAM users and assign permissions to control their access to specific cloud resources. For example, if you want website maintenance personnel in your enterprise to use VPC Endpoint resources but do not want them to delete other cloud resources or perform any other high-risk operations, you can create IAM users and grant only permissions to use VPC Endpoint resources.

If your account does not require individual IAM users for permissions management, you can skip this section.

IAM is a free service. You only pay for the resources in your account.

For more information about IAM, see `IAM Service Overview <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__.

VPC Endpoint Permissions
------------------------

New IAM users do not have any permissions assigned by default. You need to first add them to one or more groups and attach policies or roles to these groups. The users then inherit permissions from the groups and can perform specified operations on cloud services based on the permissions they have been assigned.

VPC Endpoint is a project-level service deployed for specific regions. You need to select a project for which the permissions will be granted. If you select **All projects**, the permissions will be granted for all the projects. When accessing VPC Endpoint, the users need to switch to the authorized region.

You can grant permissions by using roles or policies.

-  Roles: A coarse-grained authorization strategy provided by IAM to assign permissions based on users' job responsibilities. Only a limited number of service-level roles are available for authorization. Cloud services depend on each other. When you grant permissions using roles, you also need to attach any existing role dependencies. Roles are not ideal for fine-grained authorization and least privilege access.
-  Policies: A fine-grained authorization strategy that defines permissions required to perform operations on specific cloud resources under certain conditions. This type of authorization is more flexible and is ideal for least privilege access. For example, you can grant users only the permissions to manage a certain type of VPC Endpoint resources. Most fine-grained policies contain permissions for specific APIs. For the API actions supported by VPC Endpoint, see "Permissions Policies and Supported Actions" in *VPC Endpoint API Reference*.

:ref:`Table 1 <vpcep_pd_0001__en-us_topic_0173475706_en-us_topic_0170232209_table481412518317>` lists all system-defined permissions for VPC Endpoint.

.. _vpcep_pd_0001__en-us_topic_0173475706_en-us_topic_0170232209_table481412518317:

.. table:: **Table 1** System-defined permissions for VPC Endpoint

   +----------------------------+------------------------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------+
   | Role/Policy Name           | Description                                                                                                | Type                  | Dependency                                                                                                                 |
   +============================+============================================================================================================+=======================+============================================================================================================================+
   | VPCEndpoint Administrator  | Full permissions for VPC Endpoint                                                                          | System-defined role   | This role depends on **DNS Administrator**, **Server Administrator**, and **VPC Administrator** roles in the same project. |
   +----------------------------+------------------------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------+
   | VPCEndpoint FullAccess     | Full permissions for VPC Endpoint                                                                          | System-defined policy | None                                                                                                                       |
   +----------------------------+------------------------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------+
   | VPCEndpoint ReadOnlyAccess | Read-only permissions for VPC Endpoint. Users with these permissions can only view VPC Endpoint resources. | System-defined policy | None                                                                                                                       |
   +----------------------------+------------------------------------------------------------------------------------------------------------+-----------------------+----------------------------------------------------------------------------------------------------------------------------+

:ref:`Table 2 <vpcep_pd_0001__table6721119192915>` lists the common operations supported by system-defined permissions for VPC Endpoint.

.. _vpcep_pd_0001__table6721119192915:

.. table:: **Table 2** Common operations supported by system-defined permissions

   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Operation                                                        | VPCEndpointFullAccess | VPCEndpointReadOnlyAccess | VPCEP Administrator |
   +==================================================================+=======================+===========================+=====================+
   | Creating a VPC endpoint service                                  | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Deleting a VPC endpoint service                                  | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Querying a VPC endpoint service                                  | Y                     | Y                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Modifying a VPC endpoint service                                 | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Accepting or rejecting a VPC endpoint for a VPC endpoint service | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Adding or removing a whitelist record                            | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Creating a VPC endpoint                                          | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Deleting a VPC endpoint                                          | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Modifying a VPC endpoint                                         | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Querying a VPC endpoint                                          | Y                     | Y                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Configuring access control for a VPC endpoint                    | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Adding or deleting a resource tag                                | Y                     | x                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+
   | Querying resource tags                                           | Y                     | Y                         | Y                   |
   +------------------------------------------------------------------+-----------------------+---------------------------+---------------------+

Helpful Links
-------------

-  `IAM Service Overview <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0026.html>`__

-  :ref:`Creating a User and Granting VPC Endpoint Permissions <vpcep_ug_0003>`
-  For actions supported by fine-grained policies, see "Permissions Policies and Supported Actions" in the *VPC Endpoint API Reference*.
