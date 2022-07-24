# Hello world with env variables
- Need to be created an environment varible named "TF_VAR_[variable_name]"
- In this case: TF_VAR_HELLO_TEXT. e.g.
	```
	export TF_VAR_HELLO_TEXT='Hello secret env var text!'
	echo $TF_VAR_HELLO_TEXT
	terraform apply
	```
