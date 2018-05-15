EXTRA_DIST = \
	LICENSE.CC \
	LICENSE.GPL \
	README.md

MOSTLYCLEANFILES = \
	gtk-3.0/gtk.gresource \
	gtk-3.0/gtk-contained.css \
	gtk-3.0/gtk-contained-dark.css

themedir = $(datadir)/themes/Minions
icondir = $(datadir)/icons/Minions
cursordir = $(datadir)/icons/Unicorn
SASS = sass

all: clean compile

clean-local:
	rm -rf $(srcdir)/gtk-3.0/.sass-cache

compile:
	$(SASS) --update --sourcemap=none $(srcdir)/gtk-3.0
	glib-compile-resources --sourcedir=$(srcdir)/gtk-3.0 $(srcdir)/gtk-3.0/gtk.gresource.xml

install-data-hook:
	$(MKDIR_P)				$(DESTDIR)$(themedir)
	$(MKDIR_P)				$(DESTDIR)$(themedir)/gtk-3.0

	$(MKDIR_P)				$(DESTDIR)$(icondir)

	cp -r $(srcdir)/gtk-2.0			$(DESTDIR)$(themedir)
	cp -r $(srcdir)/gtk-3.0			$(DESTDIR)$(themedir)
#	cp    $(srcdir)/gtk-3.0/gtk.css		$(DESTDIR)$(themedir)/gtk-3.0
#	cp    $(srcdir)/gtk-3.0/gtk.gresource	$(DESTDIR)$(themedir)/gtk-3.0
#	cp    $(srcdir)/gtk-3.0/settings.ini	$(DESTDIR)$(themedir)/gtk-3.0
	cp -r $(srcdir)/metacity-1		$(DESTDIR)$(themedir)
	cp -r $(srcdir)/unity			$(DESTDIR)$(themedir)
	cp -r $(srcdir)/gnome-shell		$(DESTDIR)$(themedir)
	cp -r $(srcdir)/xfce-notify-4.0		$(DESTDIR)$(themedir)
	cp -r $(srcdir)/xfwm4			$(DESTDIR)$(themedir)
	cp    $(srcdir)/index.theme		$(DESTDIR)$(themedir)
	cp -r $(srcdir)/plank			$(DESTDIR)$(themedir)
	cp -r $(srcdir)/icons/places	$(DESTDIR)$(icondir)/
	cp -r $(srcdir)/cursor			$(DESTDIR)$(cursordir)
	cp    $(srcdir)/icon.theme      $(DESTDIR)$(icondir)/index.theme
	gtk-update-icon-cache $(DESTDIR)$(icondir)

activate:
#	Hardcore switch for testing
	sed -i "s/^button-icon=.*$$/button-icon=start-here/" ~/.config/xfce4/panel/whiskermenu-8.rc
	xfconf-query -c xsettings -p /Net/IconThemeName -s "Minions"
	xfconf-query -c xsettings -p /Net/ThemeName -s "Minions"
	xfconf-query -c xsettings -p /Gtk/CursorThemeName -s "Unicorn"
	xfce4-panel -r

uninstall-hook:
	test -e $(DESTDIR)$(themedir) && rm -rfv $(DESTDIR)$(themedir)
