## yawsi ec2 rdp-windows

RDP into Windows

### Synopsis


RDP into a EC2 instance running Windows

	yawsi ec2 rdp-windows i-0121212
	

```
yawsi ec2 rdp-windows [flags]
```

### Options

```
  -h, --help                  help for rdp-windows
  -k, --key-path string       Private Key to decrypt the password
      --rdp-password string   RDP password
      --show-command          Only display the OS command to execute
      --tag-keys string       Tag keys to filter by (tag1, tags)
  -t, --tags string           Tags to filter by (tag1:value1, tag2:value2)
      --use-private-ip        Use Private IP address (default true)
      --use-public-ip         Use Public IP address
```

### SEE ALSO
* [yawsi ec2](yawsi_ec2.md)	 - Commands for working with AWS EC2

###### Auto generated by spf13/cobra on 14-Jun-2019
