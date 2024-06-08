## create a bucket

```sh
aws s3 mb s3://encryption-fun-41
```

## create a file

```sh
echo "Hello World" > hello.txt
aws s3 cp hello.txt s3://encryption-fun-41
```

## put object with encryption of KMS

aws s3api put-object
--bucket encryption-fun-41
--key hello.txt 
--body hello.txt
--server-side-encryption aws:kms
--sse-kms