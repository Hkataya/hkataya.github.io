---
title: "Automation With JavaScript: Node FS"
date: 2020-07-12T12:14:34+06:00
image: "images/blog/node-fs.jpg"
description: "Automaion with javascript is a series of tutorials showing how easy it is to automate daily tasks using javaScript and Node.js"
---

Prior to Node js, accessing your local filesystem using javaScript was not possible due to security reasons. Now, with the built in fs module in Node, accessing the local filesystem is easier than its ever been. If you dont know what Node js is, its highly recommended to check it out before following along.

In this post we will be building a file organizer.


Alright! lets get started.

First of all, what is the fs module?

the Node fs module is a built in module that provides useful functions to interact with the file system.

To use the module all you have to do is require it.

{{< highlight "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
const fs = require("fs");
{{< / highlight >}}

Great! now lets check out some of the functions that the module provides for working with the file system:

{{< highlight "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
fs.access(): check if the file exists and Node can access it with its permissions
fs.appendFile(): append data to a file. If the file does not exist, it’s created
fs.chmod(): change the permissions of a file specified by the filename passed. Related: fs.lchmod(), fs.fchmod()
fs.chown(): change the owner and group of a file specified by the filename passed. Related: fs.fchown(), fs.lchown()
fs.close(): close a file descriptor
fs.copyFile(): copies a file
fs.createReadStream(): create a readable file stream
fs.createWriteStream(): create a writable file stream
fs.link(): create a new hard link to a file
fs.mkdir(): create a new folder
fs.mkdtemp(): create a temporary directory
fs.open(): set the file mode
fs.readdir(): read the contents of a directory
fs.readFile(): read the content of a file. Related: fs.read()
fs.readlink(): read the value of a symbolic link
fs.realpath(): resolve relative file path pointers (., ..) to the full path
fs.rename(): rename a file or folder
fs.rmdir(): remove a folder
fs.stat(): returns the status of the file identified by the filename passed. Related: fs.fstat(), fs.lstat()
fs.symlink(): create a new symbolic link to a file
fs.truncate(): truncate to the specified length the file identified by the filename passed. Related: fs.ftruncate()
fs.unlink(): remove a file or a symbolic link
fs.unwatchFile(): stop watching for changes on a file
fs.utimes(): change the timestamp of the file identified by the filename passed. Related: fs.futimes()
fs.watchFile(): start watching for changes on a file. Related: fs.watch()
fs.writeFile(): write data to a file. Related: fs.write();
{{< / highlight >}}

To access the direcory we use fs.readdir()

{{< highlight "linenos=table,hl_lines=8 15-17,linenostart=1" >}}
fs.readdir("path", function(err, par){
//this allows access to the directory and returns par(files in directory)
});
{{< / highlight >}}

Creating a folder is done by using fs.mkdir();