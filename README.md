# Auto-Complete project

## Overview
In this project, I implemented a auto-complete search tools based on N-Gram model using Hadoop MapReduce and Java language.

## Main Steps

* Build a N-gram Libraray from wiki data sets.

* According to the probability build a Language Model.

* Load the data form Language Model to MySql database.

* Using PHP, Ajax, JQuery tech to show the data from database, return the results to the web interface.

## Web Interface

Demo looks like


![](pic/demo.png)

## Deploy
First we need deploy a hadoop cluster on Docker, this cluster has one Masternode and two slavenodes. The whole project is based on the docker.

There are two Mapreduce jobs exist in this project, the first one is to process the raw data and build a N-gram library. The second one is to calculate the probabilily for every following words and load the results to databases.

I use [MAMP](https://www.mamp.info/en/) tools to solve the connections problem between hadoop cluster on docker to local database and localhost to database.

```
$ hadoop com.sun.tools.javac.Main *.java
$ jar cf ngram.jar *.class
$ hadoop jar ngram.jar Driver input /output 4 5 5
```

* args0: input path
* args1: output path
* args2: ngram size
* args3: threshold size, it would be ignored if the count of the word's occurrence smaller than threshold. 
* args4: following word size


