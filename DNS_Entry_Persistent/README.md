# Make Linux /etc/resolv.conf DNS entries persistent in RHEL 7.x, SUSE 11&12, Ubuntu, CentOS 7.x
This blog post explains about steps by step configurations of making DNS entries persistent using the /etc/resolv.conf file, With the new versions of Linux Operating Systems we have observed that /etc/resolv.conf is no more manually editable and is maintained by NetworkManager and or netconfig.  This blog explains about the steps for taking over control of /etc/resolv.conf file with different flavors and version of Linux.  Follow these steps to make DNS entries persistent on your linux operating system.

# A)  Steps to make DNS Entry persistent in RedHat Enterprise Linux Server 7.7 and 7.8

   1.  Edit the file /etc/NetworkManager/NetworkManager.conf and add the entry dns=none just after the [main] line in the file

	Final output should be looking like :-
       	...
	      [main]
	      dns=none
 	      #plugins=ifcfg-rh,ibft
	      ...
   2.  Save the file and Exit
   3.  Make DNS server entries according to your requirements into the /etc/resolv.conf file
   
	nameserver 8.8.8.8
	nameserver 8.8.4.4

   4. Save the file and Exit
   5.  Reboot the server once and check if DNS entries are persist post reboot

