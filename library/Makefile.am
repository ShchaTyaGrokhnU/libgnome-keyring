libgnomekeyringincludedir = $(includedir)/gnome-keyring-1/

lib_LTLIBRARIES=libgnome-keyring.la

INCLUDES= \
	-DPREFIX=\""$(prefix)"\" \
	-DBINDIR=\""$(bindir)"\" \
	-DLIBEXECDIR=\""$(libexecdir)"\" \
	-DGNOMELOCALEDIR=\""$(datadir)/locale"\" \
	-I$(top_srcdir) \
	-I$(top_builddir) \
	$(LIBRARY_CFLAGS) \
	$(GLIB_CFLAGS)

libgnome_keyring_la_SOURCES = \
	gnome-keyring.c \
	gnome-keyring.h \
	gnome-keyring-memory.h \
	gnome-keyring-memory.c \
	gnome-keyring-private.h \
	gnome-keyring-result.h \
	gnome-keyring-utils.c

libgnomekeyringinclude_HEADERS = \
	gnome-keyring.h \
	gnome-keyring-memory.h \
	gnome-keyring-result.h

libgnome_keyring_la_LIBADD = \
	$(top_builddir)/egg/libegg.la \
	$(LIBRARY_LIBS) \
	$(GLIB_LIBS)

libgnome_keyring_la_LDFLAGS = \
	-version-info $(LIB_GNOME_KEYRING_LT_VERSION) \
	-no-undefined -export-symbols-regex 'gnome_keyring_|GNOME_KEYRING_'

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = gnome-keyring-1.pc

EXTRA_DIST = \
	gnome-keyring-1-uninstalled.pc.in

if WITH_TESTS
TESTS_DIR = tests
else
TESTS_DIR =
endif

SUBDIRS = . \
	$(TESTS_DIR)