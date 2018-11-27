---
title: Code Scrapbook
layout: article
keywords: programming
summary: "This is a list of useful code tidbits I have found useful during my learning."
permalink: /code_scrapbook/
tags: [programming]
---

##### This is a list of useful code tidbits I have found useful during my learning. It can sometimes be difficult to remember exactly what that bit of code is that you used months ago, so this is a mixed bag of tools that hopefully others will also find useful.

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

'''
#!/bin/bash
'''
A script to delete all files older than 30 days in the given directory - useful when archiving data and clearing files

'''
.service and .timer files
'''
System daemon in linux used for scheduling scripts to run

'''
systemctl
'''

'''
journalctl -r
'''
List the system activity by most recent 
