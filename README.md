## Yet Another AWS Command Line Interface

This is `yawsi` - a hobby project to implement a very minimal
subset of functionalities usually offered by AWS command line clients.

## Install

```
$ go get github.com/amitsaha/yawsi
```


## Specifying AWS profile

Specify the AWS profile via the `AWS_PROFILE` environment variable.
Example setup:

```

1. Create ~/.aws/credentials of the form:

 [profile_name]
 aws_access_key_id=
 aws_secret_access_key=
 ..

 2. Create ~/.aws/config of the form:
 [profile_name]
 region=ap-southeast-2/us-east-1

 ```

## Sub-commands

All current functionalities currently are available via the `ec2` sub-command:

```
AWS_PROFILE=dev go run main.go
Yet Another AWS Command Line Interface

Usage:
  yawsi [command]

Available Commands:
  ec2         Commands for working with AWS EC2
  help        Help about any command

Flags:
  -h, --help   help for yawsi

Use "yawsi [command] --help" for more information about a command.
```

EC2 sub-commands:

```

$ AWS_PROFILE=dev yawsi ec2 help
Commands for working with AWS EC2

Usage:
  yawsi ec2 [command]

Available Commands:
  launch-more-like Launch AWS EC2 classic instance like another instance
  list-asgs        List Autoscaling Groups
  list-instances   List EC2 instances

```

## Examples

List all EC2 instances:

```
$ yawsi ec2 list-instances
i-031a7bbcfb163de12 : running : 127h8m23.809358629s : ec2-54-206-131-205.ap-southeast-2.compute.amazonaws.com : ip-10-219-32-208.ap-southeast-2.compute.internal
...

```

List all EC2 instances having certain tags:

```
$ yawsi ec2 list-instances --tags "key1:value1,key2:value2"
...
```

List all EC2 instances attached to an autoscaling group:

```
$ yawsi ec2 list-instances --asg myasgname
...
```

Launch an EC2 instance copying the configuration from another
EC2 instance:

```
$ yawsi ec2 launch-like <instance-id>
```


List all auto scaling groups:

```
$ yawsi ec2 list-ags
```

## License

See `LICENSE`.



