:original_name: vpcep_07_0001.html

.. _vpcep_07_0001:

Introduction
============

This section describes fine-grained permissions management for your VPC Endpoint resources. If your account does not need individual IAM users, you can skip over this section.

By default, new IAM users do not have any permissions assigned. You need to add a user to one or more groups and assign policies or roles to these groups. The users then inherit permissions from the groups can perform specified operations on cloud services based on the permissions they have been assigned.

You can grant users permissions using roles and policies. Roles are provided by IAM to define service-based permissions that match users' job responsibilities. Policies define API-based permissions for operations on specific resources under certain conditions, allowing for more fine-grained, secure access control of cloud resources.

.. note::

   You can use policies to allow or deny access to specific APIs.

An account has permissions to call all APIs, but IAM users must have the required permissions specifically assigned. The permissions required for calling an API are determined by the actions supported by the API. Only users who have been granted permissions allowing the actions can call the API successfully. For example, if an IAM user wants to query VPC endpoint services using an API, the user must have been granted permissions that allow the **vpcep:epservices:list** action.

Supported Actions
-----------------

VPC Endpoint provides system-defined policies that can be directly used in IAM. You can also create custom policies to supplement system-defined policies for more refined access control. Operations supported by policies are specific to APIs. The following are common concepts related to policies:

-  Permissions: statements in a policy that allow or deny certain operations
-  APIs: REST APIs that can be called by a user who has been granted specific permissions
-  Actions: specific operations that are allowed or denied in a custom policy
-  IAM projects/Enterprise projects: the authorization scope of a custom policy. A custom policy can be applied to IAM projects or enterprise projects or both. Policies that contain actions for both IAM and enterprise projects can be used and applied for both IAM and Enterprise Management. Policies that contain actions only for IAM projects can be used and applied to IAM only.

   .. note::

      In the table for supported actions, the check mark (Y) indicates that an action can take effect for the corresponding type of projects, and the cross symbol (x) indicates that an action cannot take effect.

VPC Endpoint supports the following actions that can be defined in custom policies:

-  :ref:`VPC Endpoint Services <vpcep_07_0002>`: contains actions supported by all VPC endpoint service APIs, such as the API for creating a VPC endpoint service.
-  :ref:`VPC Endpoints <vpcep_07_0003>`: contains actions supported by all VPC endpoint APIs, such as the API for creating a VPC endpoint.
-  :ref:`Resource Quotas <vpcep_07_0004>`: contains actions for querying quotas of VPC Endpoint resources.
-  :ref:`Tag <vpcep_07_0005>`: contains actions supported by all tag management APIs, such as the API for querying a resource tag.
