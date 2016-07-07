AC_INIT([enigma2-oe-alliance-plugins],[1.0])
AM_INIT_AUTOMAKE([dist-bzip2 foreign no-define tar-pax])
AC_CONFIG_HEADERS([enigma2-plugins-config.h])

# Silent rules are available since 1.11, but older versions
# are still in use. So don't use them unconditionally.
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AC_USE_SYSTEM_EXTENSIONS
AC_SYS_LARGEFILE

AC_PROG_CC
AC_PROG_CXX
m4_ifdef([LT_INIT], [LT_INIT], [AC_PROG_LIBTOOL])
AC_CONFIG_MACRO_DIR([m4])

AC_CHECK_HEADERS([dbox/fp.h dbox/lcd-ks0713.h])

AC_PATH_PROG(MSGFMT, msgfmt, AC_MSG_ERROR(Could not find msgfmt))
AC_PATH_PROG(MSGINIT, msginit, AC_MSG_ERROR(Could not find msginit))
AC_PATH_PROG(MSGMERGE, msgmerge, AC_MSG_ERROR(Could not find msgmerge))
AC_PATH_PROG(MSGUNIQ, msguniq, AC_MSG_ERROR(Could not find msguniq))
AC_PATH_PROG(XGETTEXT, xgettext, AC_MSG_ERROR(Could not find xgettext))

AM_PATH_PYTHON
AX_PYTHON_DEVEL
AX_PTHREAD

AC_ARG_WITH(arch,
	[  --with-arch=NAME box arch [[none,ah4,mipsel...]]],
	[ARCH="$withval"],[ARCH="mipsel"])
AC_SUBST(ARCH)
AC_DEFINE_UNQUOTED(ARCH,"$ARCH",[box arch])

AM_CONDITIONAL(SH4, test `echo "$ARCH" | cut -b 1-3` == "sh4")
AM_CONDITIONAL(MIPSEL, test `echo "$ARCH" | cut -b 1-6` == "mipsel")

AC_ARG_WITH(boxtype,
	[  --with-boxtype=NAME box type [[none,dm7025,dm800...]]],
	[BOXTYPE="$withval"],[BOXTYPE="dm800"])
AC_SUBST(BOXTYPE)
AC_DEFINE_UNQUOTED(BOXTYPE,"$BOXTYPE",[box type])


AM_CONDITIONAL(GIGABLUE, test `echo "$BOXTYPE" | cut -b 1-2` == "gb")



AM_CONDITIONAL(FORMULER1, test "$BOXTYPE" == formuler1)
AM_CONDITIONAL(FORMULER3, test "$BOXTYPE" == formuler3)
AM_CONDITIONAL(FORMULER4, test "$BOXTYPE" == formuler4)
AM_CONDITIONAL(G100, test "$BOXTYPE" == "g100")
AM_CONDITIONAL(GB800SOLO, test "$BOXTYPE" == "gb800solo")
AM_CONDITIONAL(GB800SE, test "$BOXTYPE" == "gb800se")
AM_CONDITIONAL(GB800UE, test "$BOXTYPE" == "gb800ue")
AM_CONDITIONAL(GB800SEPLUS, test "$BOXTYPE" == "gb800seplus")
AM_CONDITIONAL(GB800UEPLUS, test "$BOXTYPE" == "gb800ueplus")
AM_CONDITIONAL(GBQUADPLUS, test "$BOXTYPE" == "gbquadplus")
AM_CONDITIONAL(GBQUAD, test "$BOXTYPE" == "gbquad")
AM_CONDITIONAL(GB7356, test "$BOXTYPE" == "gb7356")
AM_CONDITIONAL(GBIPBOX, test "$BOXTYPE" == "gbipbox")
if test `echo "$BOXTYPE" | cut -b 1-2` == "dm"; then
	AC_DEFINE(DREAMBOX, 1, [Dreambox hardware])
fi

AM_CONDITIONAL(HAVE_TEMPFANCONTROL, test "$BOXTYPE" == dm8000 -o "$BOXTYPE" == dm800se -o "$BOXTYPE" == dm800sev2 -o "$BOXTYPE" == dm500hd -o "$BOXTYPE" == vuuno -o "$BOXTYPE" == vuultimo -o "$BOXTYPE" == vusolo2 -o "$BOXTYPE" == vuduo2 -o "$BOXTYPE" == dags1 -o "$BOXTYPE" == dags2 -o "$BOXTYPE" == dags3 -o "$BOXTYPE" == dags4 -o "$BOXTYPE" == dags5 -o "$BOXTYPE" == dags7335 -o "$BOXTYPE" == dags7362 -o "$BOXTYPE" == dags7356 -o "$BOXTYPE" == triplex)

AM_CONDITIONAL(HAVE_ARMV7A, test "$BOXTYPE" == cube)
AM_CONDITIONAL(HAVE_ARMV7AHF, test "$BOXTYPE" == hd51 -o "$BOXTYPE" == vusolo4k)
AM_CONDITIONAL(HAVE_CORTEXA9HF, test "$BOXTYPE" == wetekplay -o "$BOXTYPE" == wetekplayplus)

AC_CONFIG_FILES([
Makefile



AudioEffect/Makefile
AudioEffect/src/Makefile
AudioEffect/meta/Makefile
AudioEffect/po/Makefile



Blindscan/Makefile
Blindscan/src/Makefile
Blindscan/meta/Makefile
Blindscan/po/Makefile

DLNAServer/Makefile
DLNAServer/src/Makefile
DLNAServer/po/Makefile
DLNAServer/meta/Makefile

DMBlindscan/Makefile
DMBlindscan/src/Makefile
DMBlindscan/meta/Makefile
DMBlindscan/po/Makefile

FirmwareUpgrade/Makefile
FirmwareUpgrade/src/Makefile
FirmwareUpgrade/meta/Makefile
FirmwareUpgrade/po/Makefile



GigaBlueVFDControl/Makefile
GigaBlueVFDControl/src/Makefile
GigaBlueVFDControl/meta/Makefile
GigaBlueVFDControl/po/Makefile

HbbTV/Makefile
HbbTV/src/Makefile
HbbTV/meta/Makefile
HbbTV/po/Makefile

LCD4linux/Makefile
LCD4linux/src/Makefile
LCD4linux/src/data/Makefile
LCD4linux/src/data/Clock1/Makefile
LCD4linux/src/data/Clock2/Makefile
LCD4linux/src/data/Clock3/Makefile
LCD4linux/src/data/Clock4/Makefile
LCD4linux/src/data/Clock5/Makefile
LCD4linux/src/data/Clock6/Makefile
LCD4linux/src/meteo/Makefile
LCD4linux/src/renderer/Makefile
LCD4linux/src/wetter/Makefile
LCD4linux/src/armv7a/Makefile
LCD4linux/src/armv7ahf/Makefile
LCD4linux/src/cortexa9hf/Makefile
LCD4linux/src/mips/Makefile
LCD4linux/src/sh4/Makefile
LCD4linux/meta/Makefile
LCD4linux/po/Makefile



MultiTransCodingSetup/Makefile
MultiTransCodingSetup/src/Makefile
MultiTransCodingSetup/meta/Makefile
MultiTransCodingSetup/po/Makefile



RemoteChannelStreamConverter/Makefile
RemoteChannelStreamConverter/src/Makefile
RemoteChannelStreamConverter/po/Makefile

TransCodingSetup/Makefile
TransCodingSetup/src/Makefile
TransCodingSetup/meta/Makefile
TransCodingSetup/po/Makefile

TunerServer/Makefile
TunerServer/src/Makefile
TunerServer/meta/Makefile
TunerServer/po/Makefile



SatipClient/Makefile
SatipClient/src/Makefile
SatipClient/po/Makefile
SatipClient/meta/Makefile



StreamTV/Makefile
StreamTV/src/Makefile
StreamTV/meta/Makefile
StreamTV/po/Makefile
StreamTV/icons/Makefile



VuRemote/Makefile
VuRemote/src/Makefile
VuRemote/meta/Makefile
VuRemote/po/Makefile

VuDuoFanControl/Makefile
VuDuoFanControl/src/Makefile
VuDuoFanControl/meta/Makefile
VuDuoFanControl/po/Makefile

WebBrowser/Makefile
WebBrowser/src/Makefile
WebBrowser/meta/Makefile
WebBrowser/keymap/Makefile
WebBrowser/icons/Makefile
WebBrowser/po/Makefile

WirelessAccessPoint/Makefile
WirelessAccessPoint/src/Makefile
WirelessAccessPoint/meta/Makefile
WirelessAccessPoint/po/Makefile



])
AC_OUTPUT
