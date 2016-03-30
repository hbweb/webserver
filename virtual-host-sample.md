#Virtual Host Example for Apache - Ubuntu 

```bash

<VirtualHost *:80>
    ServerAdmin hung@quaycreative.com
    ServerName staging.whichoffices.com
    ServerAlias www.staging.whichoffices.com
    DocumentRoot /var/www/staging.whichoffices.com/html

    <Directory /var/www/staging.whichoffices.com>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride all
        Order allow,deny
        allow from all
			Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

```
