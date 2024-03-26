<p align="center">
    <img align="center" src="https://github.com/tivereidoro/assets/assets/105525310/8d298662-9874-46b0-aabc-54f837bcc6a4" alt="alx_swe" width="60"  height="60"/>
</p>

---
<div align="center">

## 0x01. NoSQL
<img src="https://img.shields.io/badge/Back-end-eed718"> &nbsp;<img src="https://img.shields.io/badge/NoSQL-3f3e42"> &nbsp;<img src="https://img.shields.io/badge/MongoDB-4db33d">
</div>

### Resources (Read or watch):
* [NoSQL Databases Explained](https://riak.com/resources/nosql-databases/)
* [What is NoSQL ?](https://www.youtube.com/watch?v=qUV2j3XBRHc)
* [MongoDB with Python Crash Course - Tutorial for Beginners](https://www.youtube.com/watch?v=E-1xI85Zog8)
* [MongoDB Tutorial 2 : Insert, Update, Remove, Query](https://www.youtube.com/watch?v=CB9G5Dvv-EE)
* [Aggregation](https://www.mongodb.com/docs/manual/aggregation/)
* [Introduction to MongoDB and Python](https://realpython.com/introduction-to-mongodb-and-python/)
* [mongo Shell Methods](https://www.mongodb.com/docs/manual/reference/method/)
* [The mongo Shell](https://www.mongodb.com/docs/manual/reference/mongo/)

### Requirements
## MongoDB Command File
* All your files will be interpreted/compiled on Ubuntu 18.04 LTS using `MongoDB` (version 4.2)
* All your files should end with a new line
* The first line of all your files should be a comment: `// my comment`
* A `README.md` file, at the root of the folder of the project, is mandatory
* The length of your files will be tested using `wc`

## Python Scripts
* All your files will be interpreted/compiled on Ubuntu 18.04 LTS using `python3` (version 3.7) and `PyMongo` (version 3.10)
* All your files should end with a new line
* The first line of all your files should be exactly `#!/usr/bin/env python3`
* A README.md file, at the root of the folder of the project, is mandatory
* Your code should use the `pycodestyle style` (version 2.5.*)
* The length of your files will be tested using `wc`
* All your modules should have a documentation (`python3 -c 'print(__import__("my_module").__doc__)'`)
* All your functions should have a documentation (`python3 -c 'print(__import__("my_module").my_function.__doc__)'`
* Your code should not be executed when imported (by using `if __name__ == "__main__"`:)

### More Info ℹ️
## Install MongoDB 4.2 in Ubuntu 18.04
[Official installation guide](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/)
```groovy
$ wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | apt-key add -
$ echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" > /etc/apt/sources.list.d/mongodb-org-4.2.list
$ sudo apt-get update
$ sudo apt-get install -y mongodb-org
...
$  sudo service mongod status
mongod start/running, process 3627
$ mongo --version
MongoDB shell version v4.2.8
git version: 43d25964249164d76d5e04dd6cf38f6111e21f5f
OpenSSL version: OpenSSL 1.1.1  11 Sep 2018
allocator: tcmalloc
modules: none
build environment:
    distmod: ubuntu1804
    distarch: x86_64
    target_arch: x86_64
$  
$ pip3 install pymongo
$ python3
>>> import pymongo
>>> pymongo.__version__
'3.10.1'
```
Potential issue if documents creation doesn’t work or this error: `Data directory /data/db not found., terminating` ([source](https://bryantson.medium.com/fixing-data-db-not-found-error-in-macos-x-when-starting-mongodb-d7b82abb2479) and [source](https://stackoverflow.com/questions/37702957/mongodb-data-db-not-found))

```groovy
$ sudo mkdir -p /data/db
```
Or if `/etc/init.d/mongod` is missing, please find here an example of the file:

Click to expand/hide file contents
## Use “container-on-demand” to run MongoDB
* Ask for container `Ubuntu 18.04 - MongoDB`
* Connect via SSH
* Or via the WebTerminal
* In the container, you should start MongoDB before playing with it:
```groovy
$ service mongod start
* Starting database mongod                                              [ OK ]
$
$ cat 0-list_databases | mongo
MongoDB shell version v4.2.8
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("70f14b38-6d0b-48e1-a9a4-0534bcf15301") }
MongoDB server version: 4.2.8
admin   0.000GB
config  0.000GB
local   0.000GB
bye
```
<!--
<div align="center">
    
# ♟️ Reference 📚

</div>

```groovy
#!/bin/bash

# Add MongoDB GPG key
wget -qO - https://www.mongodb.org/static/pgp/server-4.2.asc | sudo apt-key add -

# Add MongoDB repository to sources list
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.2.list > /dev/null

# Update apt packages
sudo apt-get update

# Install MongoDB
sudo apt-get install -y mongodb-org

# Check MongoDB service status
sudo service mongod status

# Display MongoDB version
mongo --version

# Install pymongo using pip3
pip3 install pymongo

# Create data directory if not exists
sudo mkdir -p /data/db

# Start MongoDB service
sudo service mongod start

# Check pymongo version in Python
python3 - <<EOF
import pymongo
print("Installed pymongo version:", pymongo.__version__)
EOF
```

This `script` performs the following tasks:

>```groovy
>   Adds the MongoDB GPG key.
>   Adds the MongoDB repository to the sources list.
>   Updates the package list.
>   Installs MongoDB.
>   Checks the MongoDB service status.
>   Displays the MongoDB version.
>   Installs pymongo using pip3.
>   Creates the /data/db directory.
>   Starts the MongoDB service.
>   Checks the pymongo version in a Python interactive session. 

* **Source: https://www.digitalocean.com/community/tutorials/how-to-install-mongodb-on-ubuntu-20-04**

    * Use this if it does not work 

<div align="center">
    
# Other one 🍿

For those having challenge installing MongoDB on  ubuntu jammy, use he command below:
</div>

```groovy
curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-archive-keyring.gpg –dearmor

echo "deb [signed-by=/usr/share/keyrings/mongodb-archive-keyring.gpg] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list


sudo apt-get update

sudo apt-get install -y mongodb-org
```
You need to check the version of your ubuntu with
> lab_release -a

Get the codename, like mine is jammy and I replace the version 4.4 to 7.0 which is the compatible one for my system. You can check that out here:
> https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/

You can proceed to start it with the appropriate command your platform uses to init which is either systemctl or service.
-->

---

#### Code Editor used: Mostly `VS-Code`; also  `Vim`
##
#### AUTHOR 👨🏽‍💻:
[_Tivere IDORO_](https://github.com/tivereidoro)

<hr>
