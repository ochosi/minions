# minions
<img title="Minions!" src="https://raw.githubusercontent.com/ochosi/minions/master/icons/places/64/start-here.png" />
<img title="Minions!" src="https://raw.githubusercontent.com/ochosi/minions/master/palette.png" />
This suite includes:

 * Minions Gtk+2/3 theme
 * Minions icon addon theme (requires elementary-xfce)
 * Unicorn cursor theme

## Ansible helper
just to do a quick test you can use ansible to activate and deactivate the theme
## Activate
```
ansible-pull -U https://github.com/ochosi/minions.git --ask-become-pass test-minions.yml
```

## Deactivate
```
ansible-pull -U https://github.com/ochosi/minions.git --ask-become-pass test-minions.yml -e deactivate=true
```

