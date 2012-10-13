AM_CPPFLAGS = -Wall $(DBUS_CFLAGS)
AM_LDFLAGS = $(DBUS_LIBS)
bin_PROGRAMS = dbus-example-server dbus-example-client

dbus_example_server_CPPFLAGS = -DG_LOG_DOMAIN=\"dbus-example-server\" $(AM_CPPFLAGS)
dbus_example_client_CPPFLAGS = -DG_LOG_DOMAIN=\"dbus-example-client\" $(AM_CPPFLAGS)

BUILT_SOURCES = server-bindings.h client-bindings.h
# We don't want to install this header
noinst_HEADERS = $(BUILT_SOURCES)

# Correctly clean the generated headers, but keep the xml description
CLEANFILES = $(BUILT_SOURCES)
EXTRA_DIST = servicename-infos.xml

#Rule to generate the binding headers
server-bindings.h:  servicename-infos.xml
	dbus-binding-tool --prefix=server_object --mode=glib-server $<> $@

client-bindings.h:  servicename-infos.xml
	dbus-binding-tool --prefix=server_object --mode=glib-client $<> $@


dbus_example_server_SOURCES = server.c server.h
dbus_example_client_SOURCES = client.c client.h
