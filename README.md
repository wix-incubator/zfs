
Description
==========

Lightweight resource and provider to manage Solaris zfs file systems. 
Currently, only a limited sub-set of options are supported.

Requirements
===========

Solaris, zfs.
Zpool should be already created, either manually or with the zpool LWRP.

Attributes
=========

    mountpoint = defaults to /name
    zoned = "on", "off" - defaults to "off"
    atime =  "on, "off", - defaults to "on"
    recordsize = defaults to "128K"
 
Usage
====

    zfs "zones/test" do
      action :create
      mountpoint "/opt/test"
    end
  
    zfs "test/test2" do
      zoned "on"
      atime "off"
      recordsize "16K"
      mountpoint "none"
    end
  
    zfs "test/test3" do
      action :destroy
    end
