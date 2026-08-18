ABOUT
=====

A radically simple Ansible role.
- System: Debian
- State: Probably Production


NOTES
=====

With **Flatpak** or **Appimage** installation don't install the nautilus plugin via **nautilus-nextcloud** because it also installs **nextcloud-desktop**.


TO DO
=====

- Config destination path should be automatically chosen based on installation type


CONFIG FILE
===========

- https://docs.nextcloud.com/server/latest/admin_manual/desktop/configfile.html


PLAYBOOK
========

```yml
# nextcloud-client
- ansible.builtin.import_role:
	name: nextcloud-client
	vars:
	nextcloud_client_user: günther
	nextcloud_client_config_force: false
	nextcloud_client_config_local_dir: /home/günther/Cloud
	nextcloud_client_config_server_user: GüntherLause
	nextcloud_client_config_server_url: https://cloud.guenther.net
	nextcloud_client_flatpak_overrides:
		Context:
		filesystems: "filesystems=xdg-run/Nextcloud;/home/{{ nextcloud_client_user }}/Cloud;!host"
```
