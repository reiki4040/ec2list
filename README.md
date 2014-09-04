ec2list
====

## Description

show your ec2 infomations with LTSV format.
this command make cache file that ec2 info. (default ~/.instance_cache.REGION)
second time, you can get ec2 info without access to AWS.

### show items
- instance_id
- name
- state
- public_ip
- private_ip
- instance_type

## Usage

show your ec2 info at ap-northeast-1

    ec2list -r ap-northeast-1

    instance_id:i-1111111	name:Name tags Value1	state:stopped	public_ip:X.X.X.X	private_ip:Y.Y.Y.Y	instance_type:t2.micro
    instance_id:i-22222222	name:Name tags Value2	state:running	public_ip:X.X.X.x	private_ip:Y.Y.Y.y	instance_type:m3.large
    ...

if you updated ec2(create new instance, stop, start and etc...), need to update cache with -f/--force option.

    ec2list -r ap-northeast-1 -f

you can set default region by AWS_REGION environment variable.

    export AWS_REGION=ap-northeast-1

## Install

### install boto

    pip install boto

### set access key (.bashrc etc...)

    export AWS_ACCESS_KEY_ID=
    export AWS_SECRET_ACCESS_KEY=

### clone ec2list and PATH

    git clone git@github.com:reiki4040/ec2list.git

    export PATH="PATH:$pathto/ec2list"

## my development env

- MacOSX 10.9.4
- Python 2.7.5
- boto 2.32.1