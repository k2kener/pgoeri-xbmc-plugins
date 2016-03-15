# Addon definition (addon.xml) #

Make sure to add a dependency to your addon definition.
e.g:
```
  <requires>
    <import addon="xbmc.python" version="1.0"/>
    <import addon="plugin.program.jdownloader" version="1.0.1"/>
  </requires>
```


# Interface #

Use the following python code to add links/container:
```
xbmc.executebuiltin('XBMC.RunPlugin(plugin://plugin.program.jdownloader/?action=addlink&url=http://www.foo.com/test.rar)')
xbmc.executebuiltin('XBMC.RunPlugin(plugin://plugin.program.jdownloader/?action=addcontainer&url=/tmp/a.dlc)')
```

Use the following python code to reconnect the internet connection:
```
xbmc.executebuiltin('XBMC.RunPlugin(plugin://plugin.program.jdownloader/?action=reconnect)')
```

# Settings #

There are two general settings for adding links/containers:

**grabber:** Should the new stuff be added to the link grabber or directly to the download list

**start:** Should the download be started afterwards

~~It would be great, if you could add a context menu entry in your plugin/script so that the user could easily modify the jd-plugin-settings~~
After giving it some thought, I would say it is good enough, if you can launch the jd-plugin itself from another plugin.

e.g.
```
xbmcaddon.Addon(id='plugin.program.jdownloader').openSettings()
```

# JD-Plugin itself #

In my opinion it would be also nice to give the user the possibility to launch the jd-plugin directly from your plugin.
```
xbmc.executebuiltin('XBMC.ActivateWindow(programs,plugin://plugin.program.jdownloader)')
```