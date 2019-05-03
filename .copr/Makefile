srpm:
	yum install -y gnutls-utils libxslt pexpect python-suds openwsman-python autoconf automake libtool
	rm -rf /tmp
	mkdir -p /tmp/_topdir/SOURCES
	cp -r ./* /tmp/_topdir/SOURCES
	rpmbuild -bs --define "_topdir /tmp/_topdir" /tmp/_topdir/SOURCES/fence-agents-vbox.spec
	cp -r /tmp/_topdir/SRPMS/* $(outdir)