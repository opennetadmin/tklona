Turnkey Linux ONA
=================

This is an initial attempt at a Turnkey linux appliance patch.

  * It will install the ONA system directly from the master branch of
the Github repo.
  * It will install the `dcm.pl` tool from Github as well

You should be able to point your browser to http://<applianceip>/ and follow
the installer steps.

You can log into the GUI as `admin` with a password of `admin` and then
create other users within the admin menu

NMAP
====

I currently have this patch enabling the Nmap ping scan tool.  What this
means is that this appliance will automatically start a daily (at 11:00am)
Nmap ping scan for ANY and all subnets you define within ONA.  If you don't
want a subnet to get scanned you must add a 'custom_attribute' to that subnet
to disable the scan.  Add the attribute `disable_nmap_scan=Y`.  The scans
are simple ICMP (ping) scans to determin if the IP is up or down.  Scanning
large subnets should take only a few seconds so this is not an intrusive scan
at all.
