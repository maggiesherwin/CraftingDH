I am using [this](https://flowingdata.com/2016/08/23/make-a-moving-bubbles-chart-to-show-clustering-and-distributions/) to learn how to create my data visualization in order to track the movement of nursing sisters in WWI. I will be using d3.js, which is a software (?) that helps create data visualization in Javascript

Set up
Creating a local host following [this](https://discussions.apple.com/docs/DOC-3083) tutorial
- Open Terminal
- `sudo vi /etc/apache2/httpd.conf`
- Enable PHP by uncommenting line 177, changing: `#LoadModule php7_module libexec/apache2/libphp7.so` to `LoadModule php7_module libexec/apache2/libphp7.so`
- Enable Perl by uncommenting line 178, changing: `#LoadModule perl_module libexec/apache2/mod_perl.so` to `LoadModule perl_module libexec/apache2/mod_perl.so`
- Enable personal websites by uncommenting the following at line 174: `#LoadModule userdir_module libexec/apache2/mod_userdir.so` to `LoadModule userdir_module libexec/apache2/mod_userdir.so`
- and do the same at line 511: `#Include /private/etc/apache2/extra/httpd-userdir.conf` to `Include /private/etc/apache2/extra/httpd-userdir.conf`
- Save and Quit
