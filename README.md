# Message of the Day

Generates a cool MOTD based on [yboetz's MOTD](https://github.com/yboetz/motd) that I found on the internet.


### Requirements

  * [update-motd](https://launchpad.net/update-motd)
  * [figlet](http://www.figlet.org/) & [lolcat](https://github.com/busyloop/lolcat) (for `10-display-name`)

### How do I set it up?

Copy the files you want in your MOTD to `/etc/update-motd.d/`. Make sure you have the `PrintMotd`
option set to `yes` in your sshd config.

The duplicate files are different versions of the same, use either one of them. E.g. `30-zpool-simple`
will not print usage bars.

The script `36-smartd` greps syslog for smartd entries to read temperature and last self-test result.
You have to enable smartd monitoring & run regular self-tests for it to display anything.

If you use `50-fail2ban` you should comment out the `compress` option in `/etc/logrotate.d/fail2ban`,
s.t. the logs are not compressed and can be grepped.
