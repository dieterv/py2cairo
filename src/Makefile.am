EXTRA_DIST = \
  wscript

# Header
pkgincludedir = $(includedir)/pycairo
pkginclude_HEADERS = pycairo.h

# Python module
pycairoexecdir = $(pyexecdir)/cairo
pycairoexec_PYTHON = __init__.py

# Python extension module
pycairoexec_LTLIBRARIES = _cairo.la
_cairo_la_CFLAGS = $(CAIRO_CFLAGS) $(PYTHON_INCLUDES)
_cairo_la_LIBADD = $(CAIRO_LIBS) $(PYTHON_LIBS)
_cairo_la_LDFLAGS = -module -avoid-version -export-symbols-regex -export-symbols-regex "_cairo|init_cairo"

if OS_WIN32
_cairo_la_LDFLAGS += \
	-no-undefined \
	-shrext ".pyd"
endif

_cairo_la_SOURCES = \
	cairomodule.c \
	context.c \
	font.c \
	path.c \
	pattern.c \
	matrix.c \
	private.h \
	pycairo.h \
	surface.c
