# SNMP Agent Example for W5500-EVB
Common to Any MCU, Easy to Add-on. Internet Offload co-Processor, HW TCP/IP chip, 
best fits for low-end Non-OS devices connecting to Ethernet for the Internet of Things. These will be updated continuously.

<!-- W5500 EVB pic -->
<p align="center">
  <img width="50%" src="http://wizwiki.net/wiki/lib/exe/fetch.php?media=products:w5500:w5500_evb:w5500-evb_side.png" />
</p>

## How to Use
This library supports only SNMP version 1. Supports PDU as follows.
  - GetRequest-PDU
  - GetNextRequest-PDU
  - GetResponse-PDU
  - SetRequest-PDU
  - SNMPv1-Trap-PDU

The SNMP agent library is roughly composed of the following functions.

- snmpd_init(): Handle the SNMP agent daemon initialization
  - Manager IP, Agent IP, H/W sockets for agent and trap  
- snmpd_run(): SNMP agent process handler in main loop (void function)

** OID examples and Settings are located in 'ioLibrary\Internet\SNMP\snmp_custom.c/h' file.

### SNMP Manager: Net-Snmp
- Net-Snmp: Open SNMPv1, SNMPv2c and SNMPv3 test suite for various OS(includes Windows and Linux)
  - http://net-snmp.sourceforge.net

- Net-Snmp Get-Request example
  - snmpget -v 1 -c public 192.168.0.112 .1.3.6.1.2.1.1.1.0 			// (sysDescr)
  - snmpget -v 1 -c public 192.168.0.112 .1.3.6.1.4.1.6.1.0 			// (Custom, get LED status)
  - snmpwalk -v 1 -c public 192.168.0.112 .1.3.6.1

- Net-Snmp Set-Request example
  - snmpset -v 1 -c public 192.168.0.112 .1.3.6.1.4.1.6.1.1 i 1			// (Custom, LED R 'On')
  - snmpset -v 1 -c public 192.168.0.112 .1.3.6.1.4.1.6.1.1 i 0			// (Custom, LED R 'Off')

## Related Project GitHub Repositories
- [W5500-EVB Main](https://github.com/Wiznet/W5500_EVB)
- [Loopback Test](https://github.com/Wiznet/Loopback_LPC11E36_LPCXpresso): Loopback test example project (TCP server / TCP client / UDP)
- [HTTP Server](https://github.com/Wiznet/HTTPServer_LPC11E36_LPCXpresso): Web server example project
- [FTP Server](https://github.com/Wiznet/FTP_LPC11E36_LPCXpresso): FTP server example project

## How to add a submodule of ioLibrary in project
- $ git submodule add git@github.com:Wiznet/ioLibrary_Driver.git project_src/ioLibrary
- $ git commit -m "description"
- $ git push

## How to clone a submodule of ioLibrary
- $ git clone git@github.com:Wiznet/SNMP_LPC11E36_LPCXpresso.git
- $ git submodule init
- $ git submodule update

## Revision History
Last release : Feb. 2015
