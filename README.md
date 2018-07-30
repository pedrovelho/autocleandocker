# autocleandocker

We sure all thank docker of its convinience. We also all know that using docker
for testing purposes may cause dangling containers that sit on the memory 
eating resources. Sometimes this is even more anoying with disk usage. When
the slash partition gets full, all the OS stop working. Trust me on that if
you have been playing with docker it is very likely you can free some space 
from `/var/lib/docker`. So this project propose is to clean docker automatically 
and periodically so you never have to bother with that again. It is ready to use 
with cron minimal environment variables, overcoming path problems and most issues
when running on the cron minimalist shell.

# Installation

First clone this repository to get the cleandocker script.

```bash
git clone https://github.com/pedrovelho/autocleandocker.git
```

Now just copy cleandocker script to your `/etc/cron.weekly` folder for a weekly clean, 
or `/etc/cron.daily` for a daily clean. Assure that file owner and group are root,
also check that the execution permission on the file. If you are in a hurry you can
just run the commands below.

```bash
sudo cp autocleandocker/cleandocker /etc/cron.weekly
sudo chown root:root /etc/cron.weekly/cleandocker
sudo chmod 755 /etc/cron.weekly/cleandocker
```

Then you can check the file permission match as below.

```bash
-rwxr-xr-x   1 root root  491 Feb 26 10:21 cleandocker
```

## News

Now we also have a autocleandockerimages, that given a certain disk threshold will
delete all docker images. 

