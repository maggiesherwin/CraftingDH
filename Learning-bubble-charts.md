I am using [this](https://flowingdata.com/2016/08/23/make-a-moving-bubbles-chart-to-show-clustering-and-distributions/) to learn how to create my data visualization in order to track the movement of nursing sisters in WWI. I will be using d3.js, which is a software (?) that helps create data visualization in Javascript

Set up
Creating a local host following [this](https://discussions.apple.com/docs/DOC-3083) tutorial
- Open Terminal
- I am using vi to edit the text documents. Similar to nano, but you place the curser on top of the character you want to delete, and press `x`
- `sudo vi /etc/apache2/httpd.conf`
- Uncomment (remove the `#`) the beginning of the line for these lines:
```
LoadModule authz_core_module libexec/apache2/mod_authz_core.so
LoadModule authz_host_module libexec/apache2/mod_authz_host.so
LoadModule include_module libexec/apache2/mod_include.so
LoadModule rewrite_module libexec/apache2/mod_rewrite.so
LoadModule php7_module libexec/apache2/libphp7.so
LoadModule perl_module libexec/apache2/mod_perl.so
LoadModule userdir_module libexec/apache2/mod_userdir.so
Include /private/etc/apache2/extra/httpd-userdir.conf
```
- Save and Quit `SHIFT+Z+Z`
- `sudo vi /etc/apache2/extra/httpd-userdir.conf`
- `#Include /private/etc/apache2/users/*.conf` to `Include /private/etc/apache2/users/*.conf`
- `SHIFT+Z+Z`
- `mkdir ~/Sites`
- `echo "<html><body><h1>My site works</h1></body></html>" > ~/Sites/index.html.en
- `cd /etc/apache2/users`
- `ls`
- Make sure `<username>.conf` is there
- `sudo vi /etc/apache2/users/<username>.conf`
- make the content
```
<Directory "/Users/<your short user name>/Sites/"> 
AddLanguage en .en 
AddHandler perl-script .pl 
PerlHandler ModPerl::Registry 
Options Indexes MultiViews FollowSymLinks ExecCGI 
AllowOverride None 
Require host localhost
</Directory>
```
- test with `apachectl configtest`
- should return `Syntax OK`
- Enter http://localhost/ into your web browser
- it should say `it works!`
- localhost/~<username> should say `My Site Works`
  
