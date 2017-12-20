# SOMTag - Freewheel Test Envvironment #
### Script Use ### 

In order to use Freewheel properly we need to spoof it into thinking we are on the discovery.de domain.

To do this please place this code inside of a Apache/Ngnix server and create a IP redirect from 127.0.0.1 to discovery.de e.g. https://coolestguidesontheplanet.com/set-virtual-hosts-apache-mac-osx-10-9-mavericks-osx-10-8-mountain-lion/



**************

### Config ###

Because Freewheel can be configured differently based on the site FW network etc. I have added some logic to allow us to switch between different configs

http://www.discovery.de/?fw=1
http://www.discovery.de/?fw=2
http://www.discovery.de/?fw=3

**************

### Migration Process: ### 
* Create a new brand:
	* This new brand is linked to the parent advertiser.
	* The new brand will contain the following fields taken from the child advertiser:
		* Name, External ID’s, Industries, Metadata, Status.
	* "User assignments" – Unique users which are present in child advertiser are added to parent advertiser. There are currently no user groups used for child advertisers.
	* Fields __NOT__ saved in new brand:
		* Address, Contacts, Discounts, Billing Terms (MRM only), Financial Info State (RPM Only)
		* These fields are not currently used by child advertisers in the Nordics.
		* Brands do not have the ability to hold these fields.
* Campaign relationships:
	* Any campaigns linked with child advertisers are changed to link to the parent advertiser.
	* All IO’s for above campaign are linked to the newly created brand.
* Agency relationships:
	* Any agencies linked with child advertisers are changed to link to the parent advertiser. Parent advertisers will have multiple associated agencies post migration.
* Creatives, network item banning and exclusions are not currently used for any child advertisers in the Nordics/DNI. For this reason I have not written a migration script for this data.