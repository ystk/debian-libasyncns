# $Id: Makefile.am 28 2007-02-16 13:51:54Z lennart $
#
# This file is part of libasyncns.
#
# libasyncns is free software; you can redistribute it and/or modify
# it under the terms of the GNU Lesser General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# libasyncns is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
# General Public License for more details.
#
# You should have received a copy of the GNU Lesser General Public License
# along with libasyncns; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA 02111-1307
# USA.

EXTRA_DIST = bootstrap.sh README LICENSE
SUBDIRS=libasyncns doc doxygen

MAINTAINERCLEANFILES=README
noinst_DATA = README

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libasyncns.pc

README:
	rm -f README
	$(MAKE) -C doc README
	cd $(srcdir) && ln -s doc/README README

homepage: all dist doxygen
	test -d $$HOME/homepage/private
	mkdir -p $$HOME/homepage/private/projects/libasyncns $$HOME/homepage/private/projects/libasyncns/doxygen
	cp libasyncns-@PACKAGE_VERSION@.tar.gz $$HOME/homepage/private/projects/libasyncns
	cp doc/README.html doc/style.css $$HOME/homepage/private/projects/libasyncns
	cp -a doxygen/html/* $$HOME/homepage/private/projects/libasyncns/doxygen
	ln -sf README.html $$HOME/homepage/private/projects/libasyncns/index.html

doxygen:
	$(MAKE) -C doxygen doxygen

.PHONY: homepage doxygen
