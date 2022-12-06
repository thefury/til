# Filtering CLI Output by Tag

You can easily filter the output of an AWS CLI call by drilling into the `tag`
sub-resource.

An example using VPCs

```bash
aws ec2 describe-vpcs --filters 'Name=tag:Name,Values=my-vpc-*'
```

