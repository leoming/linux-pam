#
# Copyright (c) 2006 Thorsten Kukuk <kukuk@thkukuk.de>
#

CLEANFILES = *~

EXTRA_DIST = README $(MANS) $(XMLS) tst-pam_loginuid

man_MANS = pam_loginuid.8

XMLS = README.xml pam_loginuid.8.xml

securelibdir = $(SECUREDIR)
secureconfdir = $(SCONFIGDIR)

AM_CFLAGS = -I$(top_srcdir)/libpam/include -I$(top_srcdir)/libpamc/include
AM_LDFLAGS = -no-undefined -avoid-version -module \
	-L$(top_builddir)/libpam -lpam
if HAVE_VERSIONING
  AM_LDFLAGS += -Wl,--version-script=$(srcdir)/../modules.map
endif

securelib_LTLIBRARIES = pam_loginuid.la

if ENABLE_REGENERATE_MAN

noinst_DATA = README

README: pam_loginuid.8.xml

-include $(top_srcdir)/Make.xml.rules
endif

TESTS = tst-pam_loginuid