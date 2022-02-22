Role Name
=========

The ansible role `Heat` is used to install and configure the Heat Beats on Windows 

Version & Author
----------------

```

VER | [ MM/DD/YYYY] | COMMENTS [AUTHOR]

1.0 | [22/01/2022] | Create Heat install role for Windows [ Ravi Singh ]
      [26/01/2022] | Update README and CHANGELOG [ Ravi Singh ]
1.1 | [11/02/2022] | Update Heat IP Address [ Ravi Singh ]
```

Requirements
------------

### OS Supported

* Windows 

### Requirements

* Heat package available in your OS software repository or stored in an ***AWS*** S3 bucket
* For Windows WINRM should be enabled 
* Vault password should be known
* AWSCLI is installed

Role Variables
--------------
| Variable | Type | Description | Required |
| ---  | ---  | ---  | --- |
| evantiheat_pkg_windows | string | Heat package version to install. For S3 download use the full package name stored in S3. | true | 
| evantiheat_s3_bucket | string   | Set ONLY if you are using an S3 bucket to store Heat install package. | true  |
| heat_folder | string   | S3 Bucket folder . | false  |
| evantiheat_s3_path | string | Folder related to s3 for heat package. | false |
| evantiheat_windows_install_dest | string | Folder where Heat binary will be installed. | true |
| heat_serveraddress | string | Server for Heat Agent to Connect to. | true |
| heat_modulelist | string | Modules to be installed for Heat Agent . | false |


Dependencies
------------

* Botocore,AWSCLI and Boto3 must be installed 
* For Windows Python ,AWSCLI and Boto3 must be installed
* For Windows WINRM should be enabled .

Example Playbook When Using OS Native Package Manager
----------------
```
- hosts: all
  roles:
    - role: heat
```

Example Windows 

```
hosts

[all]
34.241.68.25
34.245.45.252

ansible-windows ansible_connection=winrm ansible_host=35.232.181.229 ansible_password='xxxxxxxxxxxx' ansible_user=admin ansible_winrm_server_cert_validation=ignore 

eg
ansible-playbook heat.yml -i hosts --limit ansible-windows --vault-password-file /var/tmp/test
ansible-playbook -i hosts heat.yml --vault-password-file /var/tmp/test  --tags=heat
```


Support Information
-------------------


MAF Orchestration and Automation
| Support                                      | Team                                                                                                                                      |
| ---------------------| -------------------------------------------- |
| App Code:                              |MAF IAC
| DL:                  |
| GIT Project:         |
