:original_name: vpcep_07_0004.html

.. _vpcep_07_0004:

Resource Quotas
===============

.. table:: **Table 1** Actions for managing resource quotas

   +-----------------+-----------------------------+------------------+------------------+-------------+--------------------+
   | Permission      | API                         | Action           | Dependent Action | IAM Project | Enterprise Project |
   +=================+=============================+==================+==================+=============+====================+
   | Querying quotas | GET /v1/{project_id}/quotas | vpcep:quotas:get | ``-``            | Y           | X                  |
   +-----------------+-----------------------------+------------------+------------------+-------------+--------------------+
