## create bucket
aws s3 mb s3://encrypt-client-412

## create file
echo "Hello world" > hello.txt

## run our sdk ruby script
bundle exec ruby encrypt.rb

## remove bucket
aws s3 rb s3://encrypt-client-412