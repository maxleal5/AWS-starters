## get vpc id
```sh
aws ec2 describe-vpcs --filters "Name=tag:Name,Values=nacl-example-vpc" --query "Vpcs[0].VpcId" --output text
```


## Create NACL
```sh
aws ec2 create-network-acl --vpc-id vpc-04c563d82400e433e
```

## add entry
aws ec2 create-network-acl-entry \
--network-acl-id acl-06affd9164ffa940f \
--ingress \
--rule-number 90 \
--protocol -1 \
--port-range From=0,To=65535 \
--cidr-block 73.77.224.112/32 \
--rule-action deny \



## get ami for amazon linux 2
aws ec2 describe-images \
--owners amazon \
--filters "Name=name,Values=amzn2-ami-hvm-*-x86_64-gp2" \
"Name=state,Values=available" \
--query "Images[0].ImageId" \
--region us-east-2 \
--output text
