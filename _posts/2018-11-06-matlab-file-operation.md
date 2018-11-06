---
title: MatLab File Operation
layout: post
date: 2018-11-06 16:57:29 +0800
---

主要是三个函数：fopen fclose load

### **1. fopen**
```matlab
    fileID = fopen(filename)
    fileID = fopen(filename,permission)
    fileID = fopen(filename,permission,machinefmt,encoding)
    
    %permissions%
    'r': Open file for reading.
    'w': Open or create new file for writing. Discard existing contents, if any.
    'a': Open or create new file for writing. Append data to the end of the file.
    'r+':Open file for reading and writing.
    'w+':Open or create new file for reading and writing. Discard existing contents, if any.
    'a+':Open or create new file for reading and writing. Append data to the end of the file.
    'A' :Open file for appending without automatic flushing of the current output buffer.
    'W' :Open file for writing without automatic flushing of the current output buffer.
    
    %machinefmt — Order for reading or writing bytes or bits%
    Use 'n' for nagtive
    
    %encoding%
    'UTF-8' 'US-ASCII'
```

#在note的开头打开可写的in.txt：
```matlab
    fopen('in.txt','w+','n','UTF-8');
```

### **2.fclose** ###
```matlab
    fclose(fileID) closes an open file.
    fclose('all') closes all open files.
```

### **3.load** ###
```matlab
    load(filename) loads data from filename.
    load(filename,'-ascii') treats filename as an ASCII file, regardless of the file extension.
    load(filename,'-mat') treats filename as a MAT-file, regardless of the file extension.
```
#在note的开头读取in.txt:
```matlab
    load('in.txt');
```
