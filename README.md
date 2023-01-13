# Description
`pulumi login "azblob://my-storage-container?storage_account=my-storage-account"` works fine in a devcontainer on Mac OS. On Windows, the command in the exact same devcontainer fails with:

```
error: problem logging in: unable to check if bucket azblob://my-storage-container?storage_account=my-storage-account is accessible: blob (code=Unknown): DefaultAzureCredential authentication failed
GET http://169.254.169.254/metadata/identity/oauth2/token
--------------------------------------------------------------------------------
RESPONSE 403 connecting to 169.254.169.254:80: connecting to 169.254.169.254:80: dial tcp 169.254.169.254:80: connectex: A socket operation was attempted to an unreachable network.
--------------------------------------------------------------------------------
connecting to 169.254.169.254:80: connecting to 169.254.169.254:80: dial tcp 169.254.169.254:80: connectex: A socket operation was attempted to an unreachable network.
--------------------------------------------------------------------------------
```

# Steps to reproduce

1. Open this repository in VS Code (remote dev extension required)
2. Open the VS Code command palette (ctrl+shift+p) and choose "Dev Containers: Reopen in container"
3. In a terminal within VS Code, run `pulumi login "azblob://my-storage-container?storage_account=my-storage-account"` (it doesn't matter if the storage account exists or not)