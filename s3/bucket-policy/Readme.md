## Create bucket

```sh
aws s3 mb s3://bucket-policy-example-312
```

## create bucket policy
aws s3api put-bucket-policy --bucket bucket-policy-example-312 --policy file://policy.json

## in the other account access the bucket

touch bootcamp.txt
aws s3 cp bootcamp.txt s3://bucket-policy-example-312
aws s3 ls s3://bucket-policy-example-312


## cleanup

aws s3 rm s3://bucket-policy-example-312/bootcamp.txt
aws s3 rb s3://bucket-policy-example-312