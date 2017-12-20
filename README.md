# SOMTag - Freewheel Test Envvironment #
### Script Use ### 

In order to use Freewheel properly we need to spoof it into thinking we are on the discovery.de domain.

To do this please place this code inside of a Apache/Ngnix server and create a IP redirect from 127.0.0.1 to discovery.de e.g. https://coolestguidesontheplanet.com/set-virtual-hosts-apache-mac-osx-10-9-mavericks-osx-10-8-mountain-lion/



**************

### Config ###

Because Freewheel can be configured differently based on the site FW network etc. I have added some logic to allow us to switch between different configs. Please use fw=1 for general testing.

http://www.discovery.de/?fw=1

http://www.discovery.de/?fw=2

http://www.discovery.de/?fw=3

