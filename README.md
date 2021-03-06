# Wired Server 2.0

Wired Server is BBS-oriented server for UNIX-based operating systems. It uses [libwired](https://github.com/nark/libwired) and provide an implementation of the Wired 2.0 protocol. This project is a fork of the original Wired Server developed by Axel Andersson at [Zanka Software](http://zankasoftware.com/).

### Requirements

This program is mainly tested on Debian/Ubuntu Linux distributions, FreeBSD and Mac OS X. The source code is under BSD license and is totally free for use with respect of its attributed license.

To install the Wired server, you need the following prerequisites:

* **OpenSSL**: [http://www.openssl.org/source/](http://www.openssl.org/source/)
* **libxml2**: [http://xmlsoft.org/](http://xmlsoft.org/)
* **zlib**: [http://zlib.net/](http://zlib.net/)
* **git**: [http://git-scm.com/](http://git-scm.com/)

These are usually distributed with operating systems. If you need more information about installing these requirements on a specific operating system, you should visit this [page](http://www.read-write.fr/wired/wiki/howtos/install_howtos.html).

### Getting started

Installing Wired Server from sources will be done using the Autotools standard (configure, make, make install).

##### 1. Get Wired Server sources:

* On Linux:

		wget http://www.read-write.fr/wired/zip/wired.tar.gz

* On Mac OSX:

		curl -o http://www.read-write.fr/wired/zip/wired.tar.gz
		
Unarchive Wired Server sources:

	tar -xvzf wired.tar.gz

Then move to the `wired` directory:

	cd wired/

Initialize and update submodules repositories:

	git submodule update --init --recursive

Then check that the "libwired" directory was not empty.

##### 3. Run the configuration script:

During the configuration, scripts will check that your environment fills the requirements described at the top of this document. You will be warned if any of the required component is missing on your operating system.

To start configuration, use the following command:

	./configure

Wired Server is designed to be installed into `/usr/local` by default. To change this, run:

	./configure --prefix=/path	

To change the default user the installation will write files as, run:

	./configure --with-user=USER

Use `./configure --help` in order to display more options.

##### 4. Compile source code:

On GNU-like unices, type:

	make

Or, on BSD-like unices, type: 

	gmake

##### 5. Install on your system:

On GNU-like unices, type:

	make install

Or, on BSD-like unices, type: 

	gmake install


This will require write permissions to `/usr/local/`, or whatever directory you set as the prefix above. Depending of your OS setup, you may require to use `sudo`.

##### 6. Running Wired Server

To start an installed Wired server, run:

	/usr/local/wired/wiredctl start

By default a user with the login "admin" and no password is created. Use Wired Client or Wire to connect to your newly installed Wired Server. 

### Get More

If you are interested in the Wired project, check the Wired Wiki at [http://wired.read-write.fr/wiki/](http://wired.read-write.fr/wiki/)

### Troubleshootings

This implementation of the Wired 2.0 protocol is not compliant with the version of the protocol distributed by Zanka Software, for several deep technical reasons.


