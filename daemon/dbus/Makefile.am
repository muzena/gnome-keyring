
noinst_LTLIBRARIES += libgkd-dbus.la

libgkd_dbus_la_SOURCES = \
	daemon/dbus/gkd-dbus.c \
	daemon/dbus/gkd-dbus.h \
	daemon/dbus/gkd-dbus-environment.c \
	daemon/dbus/gkd-dbus-private.h \
	daemon/dbus/gkd-dbus-secrets.c \
	daemon/dbus/gkd-dbus-session.c \
	daemon/dbus/gkd-dbus-util.c \
	daemon/dbus/gkd-dbus-util.h \
	daemon/dbus/gkd-secret-change.c \
	daemon/dbus/gkd-secret-change.h \
	daemon/dbus/gkd-secret-create.c \
	daemon/dbus/gkd-secret-create.h \
	daemon/dbus/gkd-secret-dispatch.c \
	daemon/dbus/gkd-secret-dispatch.h \
	daemon/dbus/gkd-secret-error.c \
	daemon/dbus/gkd-secret-error.h \
	daemon/dbus/gkd-secret-exchange.c \
	daemon/dbus/gkd-secret-exchange.h \
	daemon/dbus/gkd-secret-introspect.c \
	daemon/dbus/gkd-secret-introspect.h \
	daemon/dbus/gkd-secret-lock.c \
	daemon/dbus/gkd-secret-lock.h \
	daemon/dbus/gkd-secret-objects.c \
	daemon/dbus/gkd-secret-objects.h \
	daemon/dbus/gkd-secret-property.c \
	daemon/dbus/gkd-secret-property.h \
	daemon/dbus/gkd-secret-prompt.c \
	daemon/dbus/gkd-secret-prompt.h \
	daemon/dbus/gkd-secret-secret.c \
	daemon/dbus/gkd-secret-secret.h \
	daemon/dbus/gkd-secret-service.c \
	daemon/dbus/gkd-secret-service.h \
	daemon/dbus/gkd-secret-session.c \
	daemon/dbus/gkd-secret-session.h \
	daemon/dbus/gkd-secret-types.h \
	daemon/dbus/gkd-secret-unlock.c \
	daemon/dbus/gkd-secret-unlock.h \
	daemon/dbus/gkd-secret-util.c \
	daemon/dbus/gkd-secret-util.h \
	$(NULL)

libgkd_dbus_la_LIBADD = \
	$(GLIB_LIBS) \
	$(GOBJECT_LIBS)

libgkd_dbus_la_CFLAGS = \
	$(DAEMON_CFLAGS) \
	$(GCR_BASE_CFLAGS) \
	$(GOBJECT_CFLAGS)

# -------------------------------------------------------------------
# TESTS

EXTRA_DIST += daemon/dbus/fixtures

noinst_LTLIBRARIES += \
	libtestservice.la

libtestservice_la_SOURCES = \
	daemon/dbus/test-service.c daemon/dbus/test-service.h

daemon_dbus_CFLAGS = \
	$(DBUS_CFLAGS) \
	$(GCR_CFLAGS)

daemon_dbus_LIBS = \
	libtestservice.la \
	libgkd-dbus.la \
	libgkd-test.la \
	libegg-test.la \
	$(GCR_BASE_LIBS) \
	$(GIO_LIBS) \
	$(GLIB_LIBS)

daemon_dbus_TESTS = \
	test-dbus-util \
	test-dbus-search \
	test-dbus-items \
	test-dbus-signals \
	test-dbus-lock

test_dbus_util_SOURCES = daemon/dbus/test-dbus-util.c
test_dbus_util_LDADD = $(daemon_dbus_LIBS)
test_dbus_util_CFLAGS = $(daemon_dbus_CFLAGS)

test_dbus_search_SOURCES = daemon/dbus/test-dbus-search.c
test_dbus_search_LDADD = $(daemon_dbus_LIBS)

test_dbus_items_SOURCES = daemon/dbus/test-dbus-items.c
test_dbus_items_LDADD = $(daemon_dbus_LIBS)

test_dbus_signals_SOURCES = daemon/dbus/test-dbus-signals.c
test_dbus_signals_LDADD = $(daemon_dbus_LIBS)
test_dbus_signals_CFLAGS = $(daemon_dbus_CFLAGS)

test_dbus_lock_SOURCES = daemon/dbus/test-dbus-lock.c
test_dbus_lock_LDADD = $(daemon_dbus_LIBS)

check_PROGRAMS += $(daemon_dbus_TESTS)
TESTS += $(daemon_dbus_TESTS)
