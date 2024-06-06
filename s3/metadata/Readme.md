## Create a bucket
aws s3 mb s3://metadata-example-413

## create a new file
echo "Hello Mars" > hello.txt

## upload file with metadata
aws s3api put-object --bucket metadata-example-413 --key hello.txt --body hello.txt --metadata Planet=Mars

## Get metadata through head object
aws s3api head-object --bucket metadata-example-413 --key hello.txt 

## cleanup
aws s3 rm s3://metadata-example-413/hello.txt
aws s3 rb s3://metadata-example-413