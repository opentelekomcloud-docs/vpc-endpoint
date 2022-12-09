:original_name: en-us_topic_0138838187.html

.. _en-us_topic_0138838187:

What Should I Do If the VPC Endpoint I Purchased Cannot Connect to a VPC Endpoint Service?
==========================================================================================

#. Confirm that the security group of the ECS NIC is correctly configured.

   -  On the ECS details page, view the security group details.
   -  Check whether the security group permits IP addresses in the 198.19.128.0/17 CIDR block in the inbound direction. If it does not, add inbound rules for this CIDR block based on service requirements.

#. Confirm that the firewall of the subnet used by the ECS NIC does not block traffic.

   If you can configure the firewall on the left part of the VPC console, confirm that the subnet of the associated VPC endpoint allows traffic to pass through.

   For details about how to disable the firewall, see `Enabling or Disabling a Firewall <https://docs.otc.t-systems.com/en-us/usermanual/vpc/vpc_acl_0011.html>`__ in the *Virtual Private Cloud User Guide*.
