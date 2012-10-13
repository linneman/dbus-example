#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.61)
AC_INIT(dbus-example, 0.1, linneman@gmx.de)
AC_CONFIG_SRCDIR([src/client.c])
AC_CONFIG_HEADER([config.h])
AC_CONFIG_MACRO_DIR([m4])

# Checks for programs.
AC_PROG_CC
PKG_PROG_PKG_CONFIG

# Checks for libraries.
PKG_CHECK_MODULES([DBUS], [dbus-glib-1])

# Checks for header files.

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.


AS_AC_EXPAND(DATADIR, $datadir)

DBUS_SERVICES_DIR="$DATADIR/dbus-1/services"
AC_SUBST(DBUS_SERVICES_DIR)
AC_DEFINE_UNQUOTED(DBUS_SERVICES_DIR, "$DBUS_SERVICES_DIR", [Where services dir for DBUS is])


AM_INIT_AUTOMAKE([subdir-objects -Wall])

# LT_PREREQ([2.2])
# LT_INIT([dlopen])

AM_PROG_CC_C_O

AC_CONFIG_FILES([Makefile
                 data/Makefile
                 src/Makefile])
AC_OUTPUT
