# AMI
This app is for pushing AMI images for Amazon EC2 instances using AWS CLI and Hashicorp Packer

Tools used:
- [Hashicorp Packer](https://www.packer.io/)


## Installation
### Packer for Linux
- Download the latest binary from here: https://www.packer.io/downloads/
- Extract zip archive
- move `packer` binary to `usr/bin/local` so that commands can be executed with `packer ...`


## Build AMI Images
### Validate template
Packer templates can be validated using
```
packer validate template.json
```
### Build template
Packer build command with command line variables takes the following form:
```
packer build \
    -var 'aws_access_key=foo' \
    -var 'aws_secret_key=bar' \
    template.json
```

## Specific to this repo
Execute `packer` command by putting below in shell script:
```
packer build \
    -var 'aws_access_key=ABCDABCD' \
    -var 'aws_secret_key=ASDASDASsdfsdASDAS' \
    -var 'ami_name=ssw590_' \
    -var 'aws_region=us-east-1' \
    -var 'subnet_id=subnet-123456fe' \
    -var 'source_ami=ami-068663a3c619dd892' \
    -var 'ssh_username=ubuntu' \
    ami.json
```
Source AMI above is a `Ubuntu 20` image.
