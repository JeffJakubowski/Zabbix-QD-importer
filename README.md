# Zabbix-QD-importer
Quick and First importer to generate a XML file to import hosts into Zabbix.

I needed a way to import a large number of basic cisco switches into zabbix, with the intent to customize templates later.
This script assumes you're using a proxy, if you're not, this script will not work.
Due to some limits within excel, importing more than 50 or so devices at once breaks the script.

Instructions:
1. Download excel file
2. Generate a list of hostnames, descriptions and IP addresses by hand or from your existing repository
3. Create a new hostgroup within Zabbix and add a device to it, any device, doesn't matter.
4. Export that host group as XML from Data Collection -> Hosts
5. Open the exported XML and obtain the uuid of your host group from the xml file
6. Edit the excel file INPUT tab, entering the host group, uuid, snmp string and proxy, data needed into the green highlighted boxes
7. Edit the device name, description and IP address on the INPUT tab
8. Critical note about excel - do not delete rows, it will break the formulas
9. on the output tab, copy the contents of cell B4 into a text editor.
    10. If cell B4 has errors, reduce the number of devices you're trying to import.... OR
    11. Instead select all cells from B6 to B99; doing this is a little more tolerant of excel cell size limits, but adds a bunch of additional whitespace.
12. Within the text editor, do a find/replace and remove all double quotes.
    13. The beginning of the file should look like this, (no starting " mark) : <?xml version='1.0' encoding='UTF-8'?>
14. Save your file and go into click import in the upper right.
