# TIL

####Silicon Valley

1. If you don't have depth, you don't exist. - Big Head is not given a position at Piep piper and then he remains unassigned at Hooli  because he doesn't add value as a person. He misses depth.
2. You need to be able to sell, technology doesn't matter, you have to be able to sell what you have. -If it wasn't was Erlich, funding would have been pulled off in the final funding deal.
3. 


####Write Excel Sheets Using Python

I use xlrd xlwt modules in python to do this. -- This was not a very good idea.

openpyxl is a better option, find a reference on how to use it in insultBot

####NodeJs

[REPL](http://www.tutorialspoint.com/nodejs/nodejs_repl_terminal.htm) 


#### To make SSH logins faster
1. Create a config file `vi ~/.ssh/config`
2. Add the following 
```
Host awshost1
Hostname publicDNSfromAWS etc.
User ubuntu
IdentityFile "link-to-the-.pem-file"
```
The .pem file before usage should be run as ` chmod 400 cloud.pem `

[This](http://www.cyberciti.biz/faq/create-ssh-config-file-on-linux-unix/) link was very useful. Thanks to Josh Holla who explained me how this works.

####File transfer with cloud computers

`rsync -avp awshost1:~/path/to/file_on_source /path/to/destination`

and 

`scp FILE.TXT awshost1:~/`

work very well.

I did come up with a hack though, I wrote a scrip that emails me the file. [Here](https://gist.github.com/rishigb/970adf227ff415eb64a879ea142ca812) is the script, ofcourse there is a lot of scope for improvement here.

I will probably use the above script to send me log files from time to time.

**NOTE: Google doesn't let you send emails via SMTP when the script is running on AWS. It will keep blocking it. Hence I took to Yahoo. But I am sure there are better ways of doing this, if you find one, please let me know **




