# vhost
Apache2 Virtual Host

Folder : /etc/apache2/sites-available
File Name : qc-portal.conf

# Inside the file : qc-portal.conf

// Place any notes or comments you have here
// It will make any customisation easier to understand in the weeks to come

// domain: domain1.com
// public: /home/demo/public_html/domain1.com/

<VirtualHost *:80>

  //Admin email, Server Name (domain name) and any aliases
  ServerAdmin webmaster@qc-portal.com
  ServerName  qc-portal.com
  ServerAlias www.qc-portal.com


  //Index file and Document Root (where the public files are located)
  //DirectoryIndex index.php
  DocumentRoot /var/www/html/qc-portal/
  
  <Directory /var/www/html/qc-portal/>
    AllowOverride All
  </Directory>


  //Custom log file locations
  LogLevel warn
  ErrorLog /var/log/apache2/error-qc-portal.com.log
  CustomLog /var/log/apache2/access-qc-portal.com.log combined

</VirtualHost>

# enable the vhost
sudo a2ensite qc-portal.com.conf

# Edit 
Type on Terminal sudo gedit /etc/hosts
add 127.0.0.1 qc-portal.com
