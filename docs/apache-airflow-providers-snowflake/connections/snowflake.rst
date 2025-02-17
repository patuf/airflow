.. Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

 ..   http://www.apache.org/licenses/LICENSE-2.0

 .. Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.



.. _howto/connection:snowflake:

Snowflake Connection
====================

The Snowflake connection type enables integrations with Snowflake.

Authenticating to Snowflake
---------------------------

Authenticate to Snowflake using the `Snowflake python connector default authentication
<https://docs.snowflake.com/en/user-guide/python-connector-example.html#connecting-using-the-default-authenticator>`_.

Default Connection IDs
----------------------

Hooks, operators, and sensors related to Snowflake use ``snowflake_default`` by default.

Configuring the Connection
--------------------------

Login
    Specify the snowflake username.

Password
    Specify the snowflake password.

Host (optional)
    Specify the snowflake hostname.

Schema (optional)
    Specify the snowflake schema to be used.

Extra (optional)
    Specify the extra parameters (as json dictionary) that can be used in the snowflake connection.
    The following parameters are all optional:

    * ``account``: Snowflake account name.
    * ``database``: Snowflake database name.
    * ``region``: Warehouse region.
    * ``warehouse``: Snowflake warehouse name.
    * ``role``: Snowflake role.
    * ``authenticator``: To connect using OAuth set this parameter ``oath``
    * ``private_key_file``: Specify the path to the private key file.
    * ``session_parameters``: Specify `session level parameters
      <https://docs.snowflake.com/en/user-guide/python-connector-example.html#setting-session-parameters>`_

When specifying the connection in environment variable you should specify
it using URI syntax.

Note that all components of the URI should be URL-encoded.

Example connection string:

.. code-block:: bash

   export AIRFLOW_CONN_SNOWFLAKE_DEFAULT='snowflake://user:password@snowflake.example/db-schema?account=account&database=snow-db&region=us-east&warehouse=snow-warehouse'
