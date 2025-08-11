# Zabbix-QD-importer
Quick and First importer to generate a XML file to import hosts into Zabbix.

I needed a way to import a large number of basic cisco switches into zabbix, with the intent to customize templates later.

Instructions:
1. Download excel file
2. Generate a list of hostnames, descriptions and IP addresses by hand or from your existing repository
3. Create a new hostgroup within Zabbix and add a device to it, any device, doesn't matter.
4. Export that host group as XML from Data Collection -> Hosts
5. Open the exported XML and obtain the uuid of your host group from the xml file
