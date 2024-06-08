## Create website 1
## create a bucket
```sh
aws s3 mb s3://cors-fun-511
```
## change block public access
```sh
aws s3api put-public-access-block \
--bucket cors-fun-511 \
--public-access-block-configuration "BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=false,RestrictPublicBuckets=false"
```

## create bucket policy
```sh
aws s3api put-bucket-policy --bucket cors-fun-511 --policy file://bucket-policy.json
```
## turn on static website hosting
```sh
aws s3api put-bucket-website --bucket cors-fun-511 --website-configuration file://website.json
```

## upload our index.html file and include a resource that is cross-origin
```sh
aws s3 cp index.html s3://cors-fun-511
```

## view the website and see if the index.html is there
http://cors-fun-511.s3-website.us-east-2.amazonaws.com


## ## create website 2

```sh
aws s3 mb s3://cors-fun2-511
```
## change block public access
```sh
aws s3api put-public-access-block \
--bucket cors-fun2-511 \
--public-access-block-configuration "BlockPublicAcls=true,IgnorePublicAcls=true,BlockPublicPolicy=false,RestrictPublicBuckets=false"
```

## create bucket policy
```sh
aws s3api put-bucket-policy --bucket cors-fun2-511 --policy file://bucket-policy2.json
```
## turn on static website hosting
```sh
aws s3api put-bucket-website --bucket cors-fun2-511 --website-configuration file://website.json
```

## upload our javascript file
aws s3 cp hello.js s3://cors-fun2-511

## upload our index.html file and include a resource that is cross-origin
```sh
aws s3 cp index.html s3://cors-fun2-511
```

## create API gateway with mock response and then test endpoint

curl -X POST -H "Content-Type: application/json" https://98rgsm28nk.execute-api.us-east-2.amazonaws.com/prod/hello

## set cors on our bucket
aws s3api put-bucket-cors --bucket cors-fun-511 --cors-configuration file://cors.json
