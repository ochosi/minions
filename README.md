# minions
Minions Gtk+ theme

## Ansible helper
just to do a quick test you can use ansible to activate and deactivate the theme
## Activate
```
ansible-playbook --ask-become-pass --inventory localhost, test-minions.yml
```

## Deactivate
```
ansible-playbook --ask-become-pass --inventory localhost, test-minions.yml -e disable=true
```
