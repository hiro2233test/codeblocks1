AM_CPPFLAGS = $(WX_CXXFLAGS) \
		-I$(top_srcdir)/src/include \
		-I$(top_srcdir)/src/sdk/wxscintilla/include

pluginlibdir = $(pkglibdir)/plugins

pluginlib_LTLIBRARIES = libcb_koders.la

libcb_koders_la_LDFLAGS = @MODULE_SHARED_LDFLAGS@ -version-info 0:1:0 -no-undefined -avoid-version

libcb_koders_la_LIBADD = ../../../sdk/libcodeblocks.la $(WX_LIBS)

libcb_koders_la_SOURCES = kodersdialog.cpp \
			cb_koders.cpp

noinst_HEADERS = kodersdialog.h \
			cb_koders.h

EXTRA_DIST = $(srcdir)/*.cbp \
		wxsmith/KodersDialog.wxs \
			manifest.xml

pkgdata_DATA = cb_koders.zip
CLEANFILES = $(pkgdata_DATA)

cb_koders.zip: manifest.xml
	PWD=`pwd` cd $(srcdir) && zip $(PWD)/cb_koders.zip manifest.xml > /dev/null
