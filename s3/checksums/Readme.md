## Create new s3 bucket


```md
aws s3 mb s3://checksums-examples-ac-312
```


## create a file that we will do a checksum on


```
echo "Hello Mars" > myfile.txt
```


## get a checksum of a file for md5
```md
md5sum myfile.txt 
## 8ed2d86f12620cdba4c976ff6651637f  myfile.txt
```
## upload our file to s3 and look at its etag

``` 
aws s3 cp myfile.txt s3://checksums-examples-ac-312
aws s3api head-object --bucket checksums-examples-ac-312 --key myfile.txt
```

## upload file with different kind of checksum

```sh
sudo apt install rhash -y
rhash --crc32 --simple myfile.txt
```

```sh
cksum -o 3 -b myfile.txt
aws s3api put-object \
--bucket checksums-examples-ac-312 \
--key myfilecrc32.txt \
--body myfile.txt \
--checksum-algorithm="CRC32" \
--checksum-crc32="e7c80b87"
```