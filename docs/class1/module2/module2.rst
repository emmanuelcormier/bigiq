Module 2: Importing BIG-IP devices for Management and Inventory
===============================================================

In this module, we will learn how to import BIG-IP devices in BIG-IQ.

The first step of managing devices with BIG-IQ is device discovery. The basic discovery allows for device inventory, device health monitoring, backup and restore of the managed device, integration with F5’s iHealth service, software upgrade, and device template deployment. As part of the discovery process, you can choose to manage other parts of the BIG-IP configuration.

In this scenario, we will import a standalone BIG-IP device, review the device information available in BIG-IQ, export our inventory to a CSV file, and review that.

Adding devices to BIG-IQ inventory:

**Dependencies**

1. The BIG-IP device must be located in your network,
2. The BIG-IP device must be running a compatible version

**BIG-IP Versions**

============================ =============================
    Functional Description       Minimum BIG-IP Version
============================ =============================
    Backup / Restore                11.5.0 HF7
    Upgrade - Legacy devices        10.2.0
    Upgrade - Managed devices       11.5.0 HF7
    Licensing BIG-IP VE             11.5.0
    Licensing - WebSafe             12.0.0
    ADC Management                  11.5.1 HF4
    AFM                             11.5.2
    Access (APM)                    12.1.0
    ASM/AWAF                        11.5.3 HF1
    DNS                             12.0.0
============================ =============================


.. toctree::
   :maxdepth: 1
   :glob:

   lab*
