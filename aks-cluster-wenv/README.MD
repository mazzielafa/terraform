# AKS  with env variables
- Need to be created two environment varibles with the AZ principal credentials:
	- "TF_VAR_APPID"
	- "TF_VAR_PASSWORD"
- To generate the principal use:
	```
	az ad sp create-for-rbac --skip-assignment
	```
