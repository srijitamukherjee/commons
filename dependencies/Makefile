NAME = python-etcd
VERSION = 0.4.3

all: srpm

clean:
	rm -rf dist/
	rm -rf $(NAME)-$(VERSION).tar.gz
	rm -rf $(NAME)-$(VERSION)-1.src.rpm
	rm -fr *.log

dist:
	git clone https://github.com/jplana/python-etcd $(NAME)-$(VERSION)
	tar -zcvf python-etcd-0.4.3.tar.gz $(NAME)-$(VERSION)
	rm -fr $(NAME)-$(VERSION)

srpm: dist
	fedpkg --dist epel7 srpm

rpm:  srpm
	mock -r epel-7-x86_64 rebuild $(NAME)-$(VERSION)-1.src.rpm --resultdir=.

.PHONY: dist rpm srpm
