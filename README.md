# config-dynamic-virtual-host-apache2
config dynamic virtual host apache2


## install 'VirtualDocumentRoot'
```
sudo ln -s /etc/apache2/mods-available/vhost_alias.load /etc/apache2/mods-enabled
```


```
cd /etc/apache2/sites-available
vi your_domain.conf
```

```
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName meeypage.xyz
    ServerAlias www.meeypage.xyz


    DocumentRoot /var/www/html3/
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>

<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName meeypage.xyz
    ServerAlias *.meeypage.xyz

    UseCanonicalName Off

    #DocumentRoot /var/www/html/projects_publish/0983
    #ScriptAlias /cgi-bin/ /usr/local/apache2/cgi-bin/
    VirtualDocumentRoot /var/www/html3/projects_publish/%-3
#ErrorDocument 404 https://nghiahsgs.com
ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined

    #UseCanonicalName Off
    #DocumentRoot "/var/www/html/projects_publish/%-2"
</VirtualHost>
```






