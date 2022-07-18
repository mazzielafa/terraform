# Terratest

## Install go
- sudo add-apt-repository ppa:longsleep/golang-backports
- sudo apt update
- sudo apt install golang-go

## To configure dependencies, run:
-  go mod init "[MODULE_NAME]"
-  go mod tidy

## To run the tests:
-  go test -v -timeout 30m
