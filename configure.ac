# Initialization
AC_PREREQ([2.69])
AC_INIT([openpower-debug-collector], [1.0],[https://github.com/openbmc/openpower-debug-collector/issues])
AC_LANG([C++])
AC_CONFIG_HEADERS([config.h])
AM_INIT_AUTOMAKE([subdir-objects -Wall -Werror foreign dist-xz])
AM_SILENT_RULES([yes])

# Checks for programs.
AC_PROG_CXX
AC_PROG_INSTALL
AC_PROG_MAKE_SET

# Checks for typedefs, structures, and compiler characteristics.
AX_CXX_COMPILE_STDCXX_14([noext])
AX_APPEND_COMPILE_FLAGS([-Wall -Werror], [CXXFLAGS])

LT_INIT

# Checks for libraries.
AX_PKG_CHECK_MODULES([SYSTEMD], [], [libsystemd >= 221], [],
[AC_MSG_ERROR(["systemd required and not found."])])

# Checks for modules
PKG_CHECK_MODULES([PHOSPHOR_LOGGING], [phosphor-logging],,
 [AC_MSG_ERROR([Could not find phosphor-logging...openbmc/phosphor-logging package required])])

# Create configured output
AC_CONFIG_FILES([Makefile ])
AC_OUTPUT
