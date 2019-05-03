BUILDROOT:=$(shell [ -d "/build" ] && echo "/build" || echo ".")
TMPDIR:=$(shell mktemp -d)

srpm:
	yum install -y gnutls-utils libxslt pexpect python-suds openwsman-python autoconf automake libtool
	mkdir -p ${TMPDIR}/_topdir/SOURCES
	rm -rf ${BUILDROOT}/_topdir
	cp -r ./* ${TMPDIR}/_topdir/SOURCES

	rpmbuild -bs -D "_topdir ${TMPDIR}/_topdir" ${TMPDIR}/_topdir/SOURCES/fence-agents-vbox.spec
	cp -r ${TMPDIR}/_topdir/SRPMS/* $(outdir)
	rm -rf ${TMPDIR}