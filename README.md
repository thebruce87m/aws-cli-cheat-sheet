# awc-cli-cheat-sheet

# Install

```bash
aws configure --profile your-name
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


# SSO

## SSO Login

```bash
aws sso login --profile profile-name
```

`~/.aws/config`

```
[profile profile-name]
sso_session = session-name
sso_account_id = sso-account-id
sso_role_name = role-name
region = eu-west-1
output = json
```
