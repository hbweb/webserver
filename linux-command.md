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
  

### Working with files and folders
  + Create folders: ``` mkdir -p website.io/html website.io/logs ```  >>  "-p" To create folder and immediate folders if required.
  + Remove folder and all content inside recusively: ``` rm -rf folder-name ``` 
  + Folder size: ```  du -hs /path/to/directory ```
  + List files inside folder & showing filesize: ```  ls -lSrh  ```
  + 

## Server stuffs
The following command line and instructions are performed on Ubuntu server version 14.0 and provided by DigitalOcean.

### Enabling PHP Module

```bash
sudo a2enmod rewrite
```

### Adding domains - Virtual Hosts editing in Apache
  
  ```bash
  sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/quaycreative.com.conf
  sudo nano /etc/apache2/sites-available/quaycreative.com.conf
  ```
  Then add the following sample.. Note, all logs file are added directly inside domain folder
  
  ```
  <VirtualHost *:80>
      ServerAdmin hung@quaycreative.com
      ServerName quaycreative.com
      ServerAlias www.quaycreative.com
      DocumentRoot /var/www/quaycreative.com/public_html
      ErrorLog /var/www/quaycreative.com/logs/error.log
      CustomLog /var/www/quaycreative.com/logs/access.log combined
      
      <Directory "/var/www/quaycreative.com/public_html">
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        Allow from all
      </Directory>

  </VirtualHost>
  ```
  
  Then enable the host file and restart server
  ```bash
  sudo a2ensite quaycreative.com.conf
  sudo service apache2 restart
  ```
  
