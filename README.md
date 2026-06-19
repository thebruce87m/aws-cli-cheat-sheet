# awc-cli-cheat-sheet

# Install

```bash
aws configure --profile your-name
```


# SSO Login

```bash
aws sso login --profile profile-name
```

# Verify Install

Find version:

```bash
aws --version
```

Find out who is logged in:

Note: This will use the default profile

```bash
aws sts get-caller-identity
```

# Profiles

List profiles on system:

```bash
aws configure list-profiles
```

Then set the profile for this session:

```bash
export AWS_PROFILE=your-name

# Confirm it's correct
aws sts get-caller-identity
```



# Downloading


Download specific folders using a file with the folder names:

```bash
cat file-with-folders.txt | xargs -I % aws s3 cp s3://bucket-name/% download/% --recursive
```

# Uploading

Upload a folder:

```bash
aws s3 cp SOURCE_DIR s3://DEST_BUCKET/ --recursive
```
or sync:

```bash
aws s3 sync SOURCE_DIR s3://DEST_BUCKET/
```
