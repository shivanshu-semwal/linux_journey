# Some workaround I learned while using Linux

## Brightness not working

Needed to add a startup shell script with sudo permissions.
So I copied the file S02redirect-brightness in the /etc/rc2.d/ directory.
Note that the SO2 matter in the front of the script since the script has to be runned at last.

```sh
ln -s /etc/init.d/redirect-brightness /etc/rc2.d/S02redirect-brightness
sudo ln -s /etc/init.d/redirect-brightness /etc/rc2.d/S02redirect-brightness
sudo cp redirect-brightness /usr/local/bin/
```

