##create a bucket

aws s3 mb s3://class-example-213

## create a file
echo "Hello there" > hello.txt
aws s3 cp hello.txt s3://class-example-213 --storage-class STANDARD_IA

## clean up 

aws s3 rm s3://class-example-213/hello.txt
aws s3 rb s3://class-example-213