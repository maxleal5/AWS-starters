## Create bucket

```sh
aws s3 mb s3://bucket-policy-example-312
```

aws s3api put-bucket-policy --bucket bucket-policy-example-312 --policy file://policy.json