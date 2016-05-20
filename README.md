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

While running `node _filename- >l.txt &` , ec2 server goes crazy and stops functioning, avoid it. 

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

####Python

run script in the background using `nohup python script.py &`

Above will give you an id, to look at the status of this do `ps -e`

To kill the above script `kill id`

More info [here](http://superuser.com/questions/446808/how-to-manually-stop-a-python-script-that-runs-continuously-on-linux) .

The `if __name__ == '__main__': ` statement means that the code will only get executed if the code is run directly, not imported. In fact, if you open up the REPL and type in import foo, nothing will be printed to your screen. This is incredibly useful. It means that you can put test code inside your script as you're developing it without worrying that it will interfere with your project. Not only that, it documents to other developers how the code in that file should be used and provides a simple test to check to make sure that you're not creating errors.

Also this [link](https://districtdatalabs.silvrback.com/how-to-develop-quality-python-code) is beautiful.

If your except statement is not working, its your fault. Don't put your except statement inside a for loop. It is just stupid, really really stupid.

####File transfer with cloud computers

`rsync -avp awshost1:~/path/to/file_on_source /path/to/destination`

and 

`scp FILE.TXT awshost1:~/`

work very well.

I did come up with a hack though, I wrote a scrip that emails me the file. [Here](https://gist.github.com/rishigb/970adf227ff415eb64a879ea142ca812) is the script, ofcourse there is a lot of scope for improvement here.

I will probably use the above script to send me log files from time to time.

**NOTE: Google doesn't let you send emails via SMTP when the script is running on AWS. It will keep blocking it. Hence I took to Yahoo. But I am sure there are better ways of doing this, if you find one, please let me know **



####Shell Scripting

To find process ID 

`ps -efww | grep -w "[n]ode" | awk -vpid=$$ '$2 != pid { print $2 }'`

If it is running, it is going to retun you a number of the process.

Number of processes `pidof node|wc -c` or `pgrep node`


####CronJobs

The best way to get things working on your system it to run these. 

on an Ubuntu
`sudo crontab -e` 
Add the details on when you want your script to run.

I have realized that running a shell script on a cron job is better, since I can add multiple conditions to my shell script. [This](https://gist.github.com/rishigb/a6935a556cba911624d37a1cf7940b9d) is an example of a working shell script.
