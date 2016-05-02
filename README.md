This is a script for pre-starting (systemd or otherwise) multiple instances of Factorio servers on Linux.


#INSTALLATION

factorio-servers goes in /etc/defaults/<br>
factorio@.service goes in /lib/systemd/system/factorio@.service<br>
pre-start-factorio goes in /usr/local/bin/<br>
config.ini-template goes in $FACTORIO_PATH/servers/<br>
<br>
Once this is in place, you need to do a systemctl daemon-reload.

#CONFIGURATION

In $FACTORIO_PATH/saves/, there has to be a mapping.csv file which will map your maps names to a port.

The mapping is as follow: \<port\>,\<mapname.zip\>
####Example: 34197,frankthetank.zip

There is also a template for the configs to use with the servers (that goes in $FACTORIO_PATH/servers/) that is the template for the settings of all thes servers.


#HOW IT WORKS

Basically it just copies files around and makes sure that nothing overwrites other servers file. The initial setup links the mods to the (new) server. You can then add a mod to each servers. This way if you want "basic" mods to be installed on all servers, they will be.

####Example: systemctl start factorio@34197
