# FMC Import Tools



Two small desktop tools for creating objects in Cisco Firepower Management Center (FMC) through its REST API.



## FMC CSV Importer (`autogroupcreator_fmc` folder)



Reads a CSV file with the columns `object,type`, where the type is `url`, `ipv4` or `network` (an IP range or CIDR block). It creates the matching URL, host, range and network objects in FMC, reusing any that already exist, and adds them to a network group and a URL group. All object and group names use a prefix you choose in the window.



## FMC Microsoft 365 Endpoint Sync (`m365` folder)



Downloads the current list of Microsoft 365 endpoints from Microsoft and creates the matching URL objects in FMC. It then updates six groups (`M365_Optimize`, `M365_Allow` and `M365_Default`, each for IPv4 addresses and for URLs) that way they always reflect the latest list.



# Other features



Both tools support the ability to save credentials to a local file, as well as read from it. I would personally recommend against saving passwords in files.

Parts of the code are based on the publicly available Cisco Devnet community plugin by chivrand: https://github.com/chrivand/Firepower\_O365\_Feed\_Parser



For now, these tools do not support the ability to automate rule-creation on the Cisco FMC device, as well as to automate their deployment. 
This was an intentional security design decision.



# Things I plan on adding:



* Ability to pause a script in-progress.
* Ability to mass-delete objects by chosen name or prefix.

