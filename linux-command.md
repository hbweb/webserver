#Linux useful command lines

The perhaps of this docs is to help people like me to keep record of all useful linux command lines when it comes to deal with server admin tasks.
I ofter forget them as my daily jobs not involving much with server side of thing. Hope this would help others too.

## Basic stuffs
Anything from copy, delete, remove and dealing with VIM or NANO.. I love nano so stick with it!

### Compress / extract archive (zip, tar files)

** Compress **
  ```bash
  tar -zcvf archive-name.tar.gz directory-name
  ```
  Where 
  + -z: Compress archive using gzip program
  + -c: Create archive
  + -v: Verbose i.e display progress while creating archive
  + -f: Archive File name

** Extract **
  ```bash
  tar -zxvf filename.tar.gz /target-folder
  cd /target-folder
  ls -l
  ```
  
** Note **
We can also do this ``` tar -cvf - file1 file2 dir3 | gzip > archive.tar.gz ```
  
  

## Server stuffs

