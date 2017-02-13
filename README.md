#Linux Server Configuration 
## Udacity Fullstack Nanodegree

Linux Distribution on a virtual machine. 

This is in fulfillment for a project in the Fullstack Nanodegree. I have configured a remote server to deploy a previous project in the Nanodegree, the Shared Library Project.

### To access the project

The ip address is : `35.162.17.201`

SSH port is : `2200`

The complete url is either http://35.162.17.201 or http://ec2-35-162-17-201.us-west-2.compute.amazonaws.com

### Summary of configuration changed made and software installed

* created a new user 'grader' with the ability to sudo
* disabled root login
* updated all packages
* changed the ssh port from `22` to `2200`
* configured the UFW to deny incoming connections
* configured the UFW to allow incoming connections from SSH, HTTP and NTP
* configured timezone to UTC
* installed and configured Apache to serve mod-wsgi app
* installed and configured Postgresql
* installed git

Other software installed:
* sudo pip install httplib2
* sudo pip install requests
* sudo pip oauth2client
* sudo pip install sqlalchemy
* sudo apt-get install python-psycopg2

I then cloned my project's repository and moved the files to the correct directory, with help from [Digital Ocean][1]
I used this [Digital Ocean Reference][2] on how to deploy a flask application to guide me. 
I made the .git directory inaccessible by editing the `.htaccess` file, guided by the second answer on this [Stack Overflow][3] post.

Converting from sqlite to postgresql was done by looking it up in the [sqlalchemy docs][6]. Changing the database setup was done following steps in Ellis Enobun's [project readme][4], section J. 

Besides the links listed above, an amazing resource for this project was Ellis Enobun's super [detailed description][4] on how he completed this project, as well as this forum post on [permission denied publickey][5] (and the Udacity forums in general.)

[1]: https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-14-04#how-to-set-up-git 
[2]: https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
[3]: http://stackoverflow.com/questions/6142437/make-git-directory-web-inaccessible
[4]: https://github.com/elnobun/Linux-Server-Configuration
[5]: https://discussions.udacity.com/t/permission-denied-publickey-after-adding-grader-user-and-changing-ssh-port/207087/5
[6]: http://docs.sqlalchemy.org/en/latest/core/engines.html
