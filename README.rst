as3
===

This is a python module to simplify using the F5 Networks AS3 utility.
https://clouddocs.f5.com/products/extensions/f5-appsvcs-extension/latest/userguide/installation.html

Install using pip:

``pip install as3``

Example
-------
::

  #!/usr/bin/env python
  import as3
  t = as3.as3(host='1.1.1.1',username='admin',password='admin')
  # Check whether AS3 is installed:
  print (str(t.isInstalled()))
  # Download the latest AS3 version from Github
  print (str(t.retrieveVersion()))
  # Install a specific version on a different host - if you leave out filename it will download the latest
  t.installAS3(host='2.2.2.2',username='admin',password='admin',filename='f5-appsvcs-3.16.0-6.noarch.rpm')
  # Uninstall it
  t.uninstallAS3(host='2.2.2.2',username='admin',password='admin')

Methods
-------
* as3([debug,host,username,password,port,usetoken]) - initialise an AS3 object
* isInstalled([version,host,username,password,usetoken,port]) - Checks whether AS3 is installed. Returns version dict, True or False
* retrieveVersion([release]) - Downloads a specific release or the latest release of the RPM package
* installAS3([version,filename,host,username,password,usetoken,port]) - Installs AS3 as a package. Returns True or False
* uninstallAS3([version,filename,host,username,password,usetoken,port]) - Uninstalls current AS3 package. Returns True or False
* github(url, [method,data,useragent,stream]) - this is a helper to retrieve from github F5 repository. Return True or False
* versionToId(version) - Returns a Github object ID related to a version number. eg version is 'v3.16.0' and ID is 22093972



