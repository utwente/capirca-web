Capirca policy checker web interface
====================================

[![Build Status](https://travis-ci.org/utwente/capirca-web.svg?branch=master)](https://travis-ci.org/utwente/capirca-web)

Synopsis
--------

An easy-to-use web interface frontend to the policy checker of the Capirca "Multi-platform ACL generation system".

Dependencies
------------

 - [Python 2.7](http://www.python.org/)
 - [Capirca](http://code.google.com/p/capirca/)
 - [dnspython](http://www.dnspython.org/)

Example Installation on Ubuntu
------------------------------

For this example we'll assume you are trying to install capirca-web on a clean installation of Ubuntu Server 12.04 LTS. You may need to do something different depending on your setup. Apply common sense as necessary.

 1. Install Apache 2, Python 2.7, dnspython and unzip:  
 `sudo apt-get update && sudo apt-get install apache2 python2.7 python-dnspython unzip`
 2. Download the latest version of capirca-web:  
 `wget -O capirca-web-master.zip https://github.com/utwente/capirca-web/archive/master.zip`
 3. Unzip the archive:  
 `unzip capirca-web-master.zip`
 4. Edit the `capirca_base` variable in the `capirca-web-master/aclcheck_cgi.py` file to reflect the path of your capirca directory using your favourite editor (nano, vim etc)
 5. If the path to your cgi-bin directory is anything other than `/cgi-bin/`, edit the `cgi_script` variable in the `capirca-web-master/static/js/custom.js` file to reflect that
 6. Make sure your capirca directory is readable by the Apache `www-data` user
 7. Create a new directory under the Apache document root:  
`sudo mkdir /var/www/capirca-web`
 8. Copy the static files to the new directory:  
 `sudo cp -r capirca-web-master/static/* /var/www/capirca-web/`
 9. Copy the Python script to the Apache cgi-bin directory:  
 `sudo cp capirca-web-master/aclcheck_cgi.py /usr/lib/cgi-bin/`
 10. Make the Python script executable:  
 `sudo chmod +x /usr/lib/cgi-bin/aclcheck_cgi.py`
 11. Start watching the Apache error log in case anything goes wrong:  
 `tail -f /var/log/apache2/error.log`
 12. Open capirca-web in the browser of your choice and enjoy

Licenses
--------

 - Capirca-web is released under the [GNU General Public License Version 3](https://www.gnu.org/licenses/gpl.html)
 - jQuery is released under the [MIT License](http://en.wikipedia.org/wiki/MIT_License)
 - Open Sans is released under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)
