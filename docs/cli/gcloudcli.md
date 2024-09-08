# Google Cloud CLI Cheat Sheet

## Authentication

After creating a service account in the Google Cloud console and creating an access key, configure the gcloud CLI interactively with:

```
gcloud auth activate-service-account --key-file ~/Downloads/<KEY_FILE>.json
```

### Show the signed-in user

```
gcloud config get-value account
```

Alternatively, you can ensure the CLI is configured properly by running the following command to request a new access token for the currently logged in user:

```
gcloud auth print-identity-token
```

### CLI Version Details

```
gcloud --version
```

## Filtering and Querying



## Enumerate Storage

List all buckets in a project:

```
gcloud storage ls
```

Enumerate all objects or blobs in a bucket:

```
gcloud storage ls --recursive gs://BUCKET_NAME/**
```

## Uploading and Downloading Files from Storage

Uploading objects from files

```
gcloud storage cp OBJECT_LOCATION gs://DESTINATION_BUCKET_NAME
```

Downloading objects as files

```
gcloud storage cp gs://BUCKET_NAME/OBJECT_NAME SAVE_TO_LOCATION
```

## SSH to a Public Cloud VM

```
to do
```

## Encrypt and Decrypt Data

```
to do
```

```
to do
```