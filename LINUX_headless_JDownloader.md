# Introduction #

At the moment there is no headless mode available for the jdownloader application. However by using an virtual xserver it is no problem to start jdownloader in the background.


# Details #

First of all install **tightvncserver**, then make sure that the vncserver starts automatically on startup by creating **/etc/init.d/vncserver**:

http://wiki.ubuntuusers.de/VNC

The last step is to start jdownloader on vncserver startup, by creating the file **~/etc/xstartup**

```
#!/bin/sh

/etc/X11/Xsession &

sleep 100

sudo -u <user> <jdownloader-directory>/jd.sh &
```

You can download the jd.sh script from the linux section on http://jdownloader.org/download/index.
You will also have to modify jd.sh to your needs. (Mainly enter the jd directory)

Of course, you don't have do use the jd.sh script, you could also start jdownlader.jar directly.