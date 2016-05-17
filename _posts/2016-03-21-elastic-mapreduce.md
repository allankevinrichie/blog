---
layout:     post
title:      "Elastic MapReduce"
date:       2016-03-21
summary:    Processing NetCDF files with Hadoop.
categories: ['hadoop','mapreduce','netcdf']
author: 	Michael Saunby
project:    hadoop
thumbnail:  ""
header: ""
---

# What is Elastic MapReduce?

_Amazon Elastic MapReduce (Amazon EMR) is a web service that makes it easy to process large amounts of data efficiently. Amazon EMR uses Hadoop processing combined with several AWS products to do such tasks as web indexing, data mining, log file analysis, machine learning, scientific simulation, and data warehousing._ [emr]

# OK, so what is Hadoop?

_Apache Hadoop is an open-source software framework written in Java for distributed storage and distributed processing of very large data sets..._ [hadoop]

# The mission

The Lab team spent several weeks exploring Hadoop, with a view to seeing how this technology might be applied to some of the challenges the Met Office will likely face in the future.

# Getting started

You'd think that configuring an Open Source package, uploading some data and bashing the data about would be a fairly simple task.  However there's a lot of variables when configuring Hadoop, and with software you've never worked with before that means a lot of unknowns. Learning how to install, configure and use something this complicated takes time, so it became apparent that we'd get very little time to actually solve any problems.  Sometimes it's not even particularly easy to see what problems best lend themselves to this technology.

## Let's try batch processing some climate data

Climate scientists typically have to work with large datasets, in the sense that they typically have global coverage and may span a century or more. Faced with a collection of grids, one or more for each month from 1850, most who are faced with calculating derived values will accept the long, slow, processing in a batch that loops through all the months.
This isn't a difficult problem to solve, it's simply a chore. Firstly to set the processing job up, then to wait for it to complete, sometimes hours or days later, and then check the results and package everything up to share with others.  This all assumes nothing went wrong, a computer crash, a disk filling up, or something else unexpected.

~~~
#/bin/sh
echo hello world
~~~

## Step 0. Get the data and the tools

A great deal of climate model data is shared in as NetCDF_ [netcdf] files. A very handy collection of command line tools known as NCO_ [nco] is available from free download.

## Step 1. Understand the structure and content of your data

One of the first things you'll want to do with a new dataset is peek inside and see what's there. For large files we often need a simple summary.

~~~
ncdump -h
~~~

## Step 2. Extract something and see what it looks like

A fairly common, but quite compute intensive task, is to generate some summary statistics from a dataset. For example we might wish to plot a series of mean values for all time steps.
First  

## Step 3. Convert/process a long run of data



[emr]: http://aws.amazon.com/documentation/elastic-mapreduce/
[hadoop]: https://en.wikipedia.org/wiki/Apache_Hadoop
[netcdf]:
[nco]: http://nco.sourceforge.net/
