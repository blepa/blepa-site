+++
title = "SBT Project Directory structure"
date = "2018-05-06"
description = "Default Scala project directories structure for stb and Maven."
draft = false
categories = [ "Scala"]
tags = ["scala", "sbt", "maven"]
mtypes = "notes"
+++
Default Scala project directories structure for stb and Maven.

## Project structure ##

### Template ###

     build.sbt 
      (plugins and additional settings for sbt)
    ▾ project/
      (plugins and additional settings for sbt)            
    ▾ src/
      (source files)
        ▾ main/
          (application code)
            ▾ resources/
              (files to include in main jar here)
            ▾ scala
              (main Scala sources)
            ▾ java
              (main Java sources)
        ▾ test/
            ▾ resources/
              (files to include in test jar here)
            ▾ scala
              (test Scala sources)
            ▾ java
              (test Java sources)

### build.sbt
```
name := "project-name"
version := "1.0" 
scalaVersion := "2.11.7"
```
Check scala version: scala -version


### .gitignore
```
dist/*
target/
lib_managed/
src_managed/
project/boot/
project/plugins/project/
.history
.cache
.lib/
```

### Create structure with a shell script
```
#!/bin/sh
mkdir -p src/{main,test}/{java,resources,scala}
mkdir lib project target

# create an initial build.sbt file
echo 'name := "MyProject"
version := "1.0"
scalaVersion := "2.10.0"' > build.sbt
```
