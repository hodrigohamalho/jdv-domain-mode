# Jboss Data Virtualization in Domain Mode

## Systemctl 

In domain controller copy the `domain-controller/init.d` folder here to your $JBOSS_HOME/bin directory, it will replace your current jboss init.d, so do a backup first :)

Repeate the same process to your host-controller but use `domain-controller/init.d`.

The script that handles start/stop/restart/status operations is `jboss-data-virtualization.service`.
Adjusts the script to your installation path. Remember that this kind of script doesn't support the use of variables, 
so you need to replace all ocurrences.

Copy the file `jboss-data-virtualization.service` to `/etc/systemd/system`. 

``` 
cp jboss-data-virtualization.service /etc/systemd/system/
``` 

Enable it in startup 

```
systemctl enable jboss-data-virtualization
```

Now you can use

``` 
systemctl start|stop|restart|status jboss-data-virtualization
```
