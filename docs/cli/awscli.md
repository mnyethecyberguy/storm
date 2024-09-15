# AWS CLIv2 Cheat Sheet

## Authentication

After creating an IAM user in the AWS console and creating an access key, configure the AWS CLI interactively with:

```
aws configure
```

### Show the signed-in user

```
aws sts get-caller-identity
```

### CLI Version Details

```
aws --version
```

## Filtering and Querying



## Enumerate Storage

Enumerate all buckets in an account:

```
aws s3 ls s3://
```

Enumerate all objects or blobs in a bucket:

```
aws s3 ls s3://<BUCKET_NAME>
```

## Uploading and Downloading Files from Storage

Uploading

```
aws s3 cp file.txt s3://<BUCKET_NAME>
```

Downloading

```
aws s3 cp s3://<BUCKET_NAME>/file.txt .
```

## Key Management

Activate an access key id for an IAM user

```
aws iam update-access-key --access-key-id AKIA... --status Active --user-name <user>
```

Deactivate an access key id for an IAM user

```
aws iam update-access-key --access-key-id AKIA... --status Inactive --user-name <user>
```

Delete access key id and secret access key pair

```
aws iam delete-access-key --access-key-id <access-key-id> --user-name <user>
```

## Remote Administration

SSH to a Public Cloud VM

```
ssh ubuntu@$(aws ec2 describe-instances --filters Name=instance-state-name,Values=running Name=tag-value,Values=<INSTANCE_NAME> --query "Reservations[0].Instances[0].PublicIpAddress" --output text)
```

## Encryption and Decryption

Encrypting data

```
aws kms encrypt --key-id <KEY_ARN_OR_ALIAS> --plaintext <TEXT> | jq -r '.CiphertextBlob' | base64 -d > encrypted.txt
```

Decrypting data

```
aws kms decrypt --key-id <KEY_ARN_OR_ALIAS> --ciphertext-blob fileb://encrypted.txt | jq -r '.Plaintext'
```