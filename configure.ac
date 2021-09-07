AC_PREREQ(2.59c)

AC_INIT([pa-applet], [1.0.0], [], [pa-applet])

AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE([foreign])

AC_PROG_CC_C99
if test "x$ac_cv_prog_cc_c99" = "xno"; then
    AC_MSG_ERROR([C compiler must be C99 compliant])
fi
AC_HEADER_STDC

PKG_CHECK_MODULES([GLIB], [glib-2.0])
AC_ARG_ENABLE([gtk2], [AS_HELP_STRING([--enable-gtk2], use GTK+ 2)], [gtk=gtk+-2.0], [gtk=gtk+-3.0])
PKG_CHECK_MODULES([GTK], [$gtk])
PKG_CHECK_MODULES([LIBPULSE], [libpulse])
PKG_CHECK_MODULES([LIBPULSE_GLIB], [libpulse-mainloop-glib])
AC_ARG_WITH([libnotify], [AS_HELP_STRING([--without-libnotify], [disable notification support])], [], [with_libnotify=yes])
AS_IF([test "x$with_libnotify" == xyes], [PKG_CHECK_MODULES([LIBNOTIFY], [libnotify], [AC_DEFINE(HAVE_LIBNOTIFY, [], [Notification support])])])
PKG_CHECK_MODULES([XLIB], [x11])

AC_CONFIG_FILES([Makefile man/Makefile src/Makefile])
AC_OUTPUT
