# minions
<img title="Minions!" src="https://raw.githubusercontent.com/ochosi/minions/master/icons/places/64/start-here.png" />
<img title="Minions!" src="https://raw.githubusercontent.com/ochosi/minions/master/palette.png" />
Minions Gtk+ theme

## Ansible helper
just to do a quick test you can use ansible to activate and deactivate the theme
## Activate
```
ansible-playbook --ask-become-pass --inventory localhost, test-minions.yml
```

if you have local changes and don't want to get the newest code from github, you can use
```
ansible-playbook --ask-become-pass --inventory localhost, test-minions.yml -e local_changes=true
```

## Deactivate
```
ansible-playbook --ask-become-pass --inventory localhost, test-minions.yml -e deactivate=true
```

