---
title: Data Structures and Algorithms
layout: article
keywords: programming
summary: "My solutions to the Data Structures and Algorithms problems through Coursera."
permalink: /code_scrapbook/
tags: [programming]
---

##### This is a list of code tidbits I have found useful during my learning. It can sometimes be difficult to remember exactly what that bit of code is that you used months ago, so this is a mixed bag of tools that hopefully others will also find useful.

<br/>

#### Python
```
  python -m SimpleHTTPServer
```
Command prompt for Python for serving up local files at http://localhost:8080

<br/>

``` python
  indices = np.where(X.values == 'search criteria' )
```
Use numpy to search a pandas dataframe for a specific term. Indices contains the row(s) and column(s) of the search criteria where indices[0] would be a list of the rows and indices[1] the columns.

<br/>

``` python
  for counter, value in enumerate(some_list):
      print(counter, value)
```
`enumerate` automatically creates a counter while looping over a list.

<br/>

``` python
  x, _, y = (1, 2, 3) # x = 1, y = 3
```
The underscore can be used to ignore values when unpacking, rather than having to specify a variable that won't be used.

<br/>

``` python
zip and zip*
list_a = [1, 2, 3, 4, 5]
list_b = ['a', 'b', 'c', 'd', 'e']

zip(list_a, list_b)

Output: [(1, 'a'), (2, 'b'), (3, 'c'), (4, 'd'), (5, 'e')]
```
zip returns a single list from 2 with the ith element of each list paired up

zip* does the opposite of this

<br/>


```
  bundle exec Jekyll serve
```    
Command prompt to locally host a Jekyll repository, very useful to view changes to a website served on GitHub without committing to master.

<br/>

#### JavaScript


```
  http-server
```
A NodeJS command line HTTP server tool for serving up local files at http://localhost:8080

<br/>

#### Bash

```
#!/bin/bash

backup_path = /directory/to/backup
bucket_name = name.of.backup

aws s3 sync $backup_path s3://$bucket_name
```
A script to backup a directory to an Amazon AWS S3 storage. Can be used with a timer bash script to do this on a schedule

```
#!/bin/bash

find /path/to/directory/ -type f -name '*.csv' -mtime +30 -exec rm {} \;

find /path/to/directory/ -type d -empty -delete \;
```
First line finds file types with .csv extension and deletes them if they are older than 30 days.
The second line finds directory types that are empty and removes them.

#### Linux
.service and .timer files are system daemons in linux used for scheduling scripts to run.
Normally held in /etc/systemd/system

``` linux
[Unit]
Description = run backup.py every day at 12:00pm

[Service]
WorkingDirectory = /working/directory/path
User = root

ExecStart = /usr/bin/python3.7m /working/directory/path/python_script/backup.py
```
This is the example.service file which contains the instructions for what to do i.e. using python3.7 the backup.py script will be executed

``` linux
[Unit]
Description = run backup.py every day at 12:00pm

[Timer]
OnCalendar = *_*_* 12:00:00
Persistent = false
Unit = example.service

[Install]
WantedBy = multi-user.target
```
This is the example.timer file, which should have the same prefix as its associated service file. It specifies which service file to execute and at what time. The asterisks refer to year, month and date. A day such as 'Friday' can also be specified. If Persistent is true then if the system was turned off during a schedule execute then it will immediately run when switched back on.

``` linux
systemctl enable example.service
systemctl disable
systemctl start
systemctl stop
```
commands used to enable and start the linux bash scripts

``` linux
journalctl -r
```
List the system activity by most recent events. Useful to use with systemctl
