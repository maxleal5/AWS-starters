## create user without permissions
aws iam create-user --user-name sts-machine-user
aws iam create-access-key --user-name sts-machine-user --output table

aws configure

Test who you are 
aws sts get-caller-identity --profile sts

## Create a role

aws iam put-user-policy \
--user-name sts-machine-user \
--policy-name StsAssumePolicy \
--policy-document file://policy.json

aws sts assume-role \
--role-arn arn:aws:iam::767398019776:role/my-sts-fun-stack-StsRole-xXPtwDi3L3lw \
--role-session-name s3-sts-fun \
--profile sts


aws sts get-caller-identity --profile assumed

aws s3 ls --profile assumed

## cleanup
aws iam delete-access-key --access-key-id AKIA3FLD4QLAKAXG4OOJ --user-name sts-machine-user 
aws iam delete-user-policy --user-name sts-machine-user --policy-name StsAssumePolicy
aws iam delete-user --user-name sts-machine-user