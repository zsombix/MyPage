# MyPage
The source code of my CV page.

## Deployment

All information needed to deploy this site is at the following link: https://anthonychu.ca/post/blazor-azure-storage-static-websites/

### Some modifications:

* Have the default subscription set to the proper one in the CLI to be able to copy the files. `az account set -s "My subscription"`
* To publish the files use `dotnet publish -p:BlazorEnableCompression=false -c Release -o out`. It does not create the packaged version of the files.
* To upload the files use the following: `az storage blob upload-batch --account-name <myblazorapp> -s . -d '$web' --auth-mode login`
* Although you are an admin of the storage account you don't have the role to be able to upload files to it. You need to set it in the azure portal: Access Control (IAM) -> Add -> Add role assignment -> Set the "Storage Blob Data Contributor" role for your user.
* I have not lookied into CD. I plan to look into how to do it.
