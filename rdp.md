# RDP
## How to connect without giveing username and password all time
open the rdp file in vscode or all other editor and append this lines \
`username:s:domain\username` \
`password 51:b:myEncryptedPassword`
### how to get myEncryptedPassword
open powershell and write this \
`("MySuperSecretPassword!" | ConvertTo-SecureString -AsPlainText -Force) | ConvertFrom-SecureString` \
and copy the generated output to myEncryptedPassword
