dnl configure.in for mmc-core project.
dnl (c) 2011 mandriva, http://www.mandriva.com
dnl
dnl This file is part of Mandriva Management Console (MMC).
dnl
dnl MMC is free software; you can redistribute it and/or modify
dnl it under the terms of the GNU General Public License as published by
dnl the Free Software Foundation; either version 2 of the License, or
dnl (at your option) any later version.
dnl
dnl MMC is distributed in the hope that it will be useful,
dnl but WITHOUT ANY WARRANTY; without even the implied warranty of
dnl MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
dnl GNU General Public License for more details.
dnl
dnl You should have received a copy of the GNU General Public License
dnl along with MMC.  If not, see <http://www.gnu.org/licenses/>.
dnl Process this file with autoconf to produce a configure script.

dnl autoconf version
AC_PREREQ(2.59)

dnl autoconf initialization
AC_INIT([mmc-ldap-check-password], [3.0.3.2], [http://mds.mandriva.org])

AC_CANONICAL_BUILD
AC_CANONICAL_HOST
AC_CANONICAL_TARGET

AM_INIT_AUTOMAKE([-Wno-portability])
AM_CONFIG_HEADER(config.h) 
m4_ifdef([AM_SILENT_RULES],[AM_SILENT_RULES(yes)])
AC_CONFIG_MACRO_DIR([m4])

dnl check for programs
AC_PROG_CC
AC_PROG_MAKE_SET
AC_PROG_LN_S
AC_PROG_LIBTOOL

dnl Check for headers
AC_HEADER_STDC
# check for slap.h / portable.h headers
AC_CHECK_HEADERS([openldap/include/portable.h],,AC_MSG_ERROR(mmc-check-password requires portable.h))
AC_CHECK_HEADERS([openldap/slapd/slap.h],,AC_MSG_ERROR(mmc-check-password requires slap.h))

dnl
dnl --with-ldap-confdir
dnl   Set path to ldap configuration directory
dnl   Default to SYSCONFDIR/ldap
dnl
AC_ARG_WITH([ldap-confdir],
            [AS_HELP_STRING([--with-ldap-confdir],
                            [path to ldap configuration direcory @<:@default=SYSCONFDIR/ldap@:>@])],
            [ldapconfdir="$withval"],
	    [ldapconfdir="${sysconfdir}/ldap"])
AC_SUBST([ldapconfdir])

dnl
dnl --with-ldap-libdir
dnl   Set path to ldap plugins directory
dnl   Default to LIBDIR/ldap
dnl
AC_ARG_WITH([ldap-libdir],
            [AS_HELP_STRING([--with-ldap-libdir],
                            [path to ldap plugins direcory @<:@default=LIBDIR/ldap@:>@])],
            [ldaplibdir="$withval"],
	    [ldaplibdir="${libdir}/ldap"])
AC_SUBST([ldaplibdir])

dnl files to generate with automake
AC_CONFIG_FILES([Makefile])

dnl write all stuff
AC_OUTPUT
