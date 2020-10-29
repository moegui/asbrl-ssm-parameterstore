ASBRL-SSM-PARAMETERSTORE
=========

Create a CloudFormation Template to Deploy a groups of Parameters Store.

Requirements
------------

None


Role Variables
--------------

- TEMPLATE_DEST:
- TAGS:
    - RELEASE:
    - ENVIRONMENT_TYPE:
- PARAMETERS: (List)
    - NAME:
    - TYPE: String (Default)
    - PATH:
    - DESCRIPTION:



Dependencies
------------

None

Example Playbook
----------------

        - name: Generate {{EnvironmentType}} cf-parameters
          include_role:
            name: asbrl-ssm-parameterstore
          vars:
            TEMPLATE_DEST: ./artifacts/{{EnvironmentType}}/cf-elasticstack-parameters.yml
            TAGS:
              RELEASE: "{{Release}}"
              ENVIRONMENT_TYPE: "{{EnvironmentType}}"
            PARAMETERS:
              - NAME: Monitoring
                PATH: Elasticsearch
                DESCRIPTION: Elasticsearch Allow the monitoring node
              - NAME: AlarmDiskUsed
                PATH: Cloudwatch
                TYPE: Number
                DESCRIPTION: Cloudwatch alarm threshold for metric Disk Used

License
-------

BSD

Author Information
------------------

Moegui.com
