---
title: MatLab File Operation
layout: post
date: 2018-11-06 16:57:29 +0800

---
主要是三个函数：fopen fclose load

### **1. fopen**

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