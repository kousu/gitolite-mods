# gitolite-mods

Unofficial extensions for https://gitolite.com

## `keys` - manage

This provides account key management. Gitolite is nice but in its default config the only way to authorize new accounts is for an admin to `git clone server.example.com:gitolite-admin.git` and manually edit it, making sure to put files in the right place and tweaking the conf file appropriately.
This lets administration be done via the command line, like the rest of the interaction.

This improves on https://gitolite.com/gitolite/contrib/ukm.html and https://gitolite.com/gitolite/contrib/sskm.html.
ukm is slightly unmaintained, has a [complicated ruleset](https://gitolite.com/gitolite/contrib/ukm.html#how-to-configure-user-key-management-and-who-can-use-it); sskm only supports *self* key management, so it still imposes a burden on admins.
Both of them have [a complicated](https://gitolite.com/gitolite/contrib/ukm.html#add-a-new-key-as-a-self-key-manager) [two step](https://gitolite.com/gitolite/contrib/sskm#step-2-confirming-the-addition) process to interact with.

This works best if you enable [wildrepos](https://gitolite.com/gitolite/wild) (since otherwise the admin will still need to manually interact with `gitolite-admin.git` to create new repos) and if users use the `perms` command to grant each other access.
