## create new bucket
```sh
aws s3api create-bucket --bucket acl-example-523 --region us-east-1
```

## turn off block public access for ACLs
```sh
aws s3api put-public-access-block \
--bucket acl-example-523 \
--public-access-block-configuration "BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=true,RestrictPublicBuckets=true"
```

```sh
aws s3api get-public-access-block --bucket acl-example-523
```

## change bucket ownership

```sh
aws s3api put-bucket-ownership-controls \
--bucket acl-example-523 \
--ownership-controls="Rules=[{ObjectOwnership=BucketOwnerPreferred}]"
```

## change ACLs to allow control for user in other aws account
```sh
aws s3api put-bucket-acl --bucket acl-example-523 --access-control-policy file:///workspace/AWS-starters/s3/acls/policy.json
```

## access bucket from other account
```sh
touch hello.txt
aws s3 cp hello.txt s3://acl-example-523
aws s3 ls s3://acl-example-523
```

## cleanup
```sh
aws s3 rm s3://acl-example-523/hello.txt
aws s3 rb s3://acl-example-523
```