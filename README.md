# TIL


#### To make SSH logins faster
1. Create a config file `vi ~/.ssh/config`
2. Add the following 
```
Host awshost1
 Hostname publicDNSfromAWS etc.
User ubuntu
IdentityFile "link to the .pem file"
```
The .pem file before usage should be run as ` chmod 400 cloud.pem `

[This](http://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/) link was very useful. Thanks to Josh Holla who explained me how this works.


