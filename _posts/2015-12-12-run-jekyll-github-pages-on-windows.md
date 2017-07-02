---
layout: post
title:  "Run Jekyll (GitHub Pages) on Windows"
date:   2015-12-12 20:00:00
categories: jekyll
---
Running [Jekyll](http://jekyllrb.com) on Windows is not an easy task.
There are several guides on the web how to setup Jekyll, but this involves to install Ruby and Python on your system.
In short you will mess up your Windows installation with new tools in your `PATH`.

The other option is to use [PortableJekyll](https://github.com/madhur/PortableJekyll).
No messing up of the OS, just one folder containig everything needed.
Unfortunately it contains the wrong [versions for GitHub](https://pages.github.com/versions/) and it is huge (> 1.5 GB).

## Jekyll for GitHub Pages
After some reading I found out that setting up a portable Jekyll environment is not so hard.

### Prepare

You have to download following:

1. [ruby 2.1.7](http://dl.bintray.com/oneclick/rubyinstaller/ruby-2.1.7-i386-mingw32.7z) 
2. [DevKit 4.7.2](http://dl.bintray.com/oneclick/rubyinstaller/DevKit-mingw64-32-4.7.2-20130224-1151-sfx.exe)
3. [libcurl 7.40](http://curl.haxx.se/gknw.net/7.40.0/dist-w32/renamed-curl-7.40.0-devel-mingw32.zip)
4. [Python 2.7.11](https://www.python.org/ftp/python/2.7.11/python-2.7.11.msi)

### Environment

1. create a new folder `github-pages` that will contain our new GitHub Pages environment
2. extact ruby to `github-pages` and rename the created folder to `ruby`
3. extact devkit to `github-pages` into a new `devkit` folder
4. extract curl to `github-pages` and rename the created folder to `curl`
5. execute `msiexec /a python-2.7.11.msi` in your download folder
6. cut `C:\Pyhton27` folder and paste it into `github-pages` and rename it to `python`

### Config

In your `github-pages` folder create a new text file `setpath.cmd`:

```
@ECHO OFF
ECHO Adding Jekyll to PATH...

SET RUBY_PATH=%~dp0ruby
SET DEVKIT_PATH=%~dp0devkit
SET CURL_PATH=%~dp0curl
SET PYTHON_PATH=%~dp0python

SET PATH=%RUBY_PATH%\bin;%DEVKIT_PATH%\bin;%DEVKIT_PATH%\mingw\bin;%CURL_PATH%\bin;%PYTHON_PATH%;%PATH%
```

### Jekyll

Now we can install Jekyll and it's dependencies:

1. open a command prompt (`cmd`)
2. execute `setpath.cmd`
3. execute `gem install github-pages`
4. execute `gem install wdm`

### Done

We are finished and can test our GitHub Pages compatible portable Jekyll setup.
