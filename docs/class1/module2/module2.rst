Module 2: Importing BIG-IP devices for Management and Inventory
===============================================================

In this module, we will learn how to import BIG-IP devices in BIG-IQ.

The first step of managing devices with BIG-IQ is device discovery. The basic discovery allows for device inventory, device health monitoring, backup and restore of the managed device, integration with F5’s iHealth service, software upgrade, and device template deployment. As part of the discovery process, you can choose to manage other parts of the BIG-IP configuration.

In this scenario, we will import one member of an existing BIG-IP cluster, review the device information available in BIG-IQ, export our inventory to a CSV file, and review that.

Adding devices to BIG-IQ inventory:

**Dependencies**

1. The BIG-IP device must be located in your network,
2. The BIG-IP device must be running a compatible version
3. Port 22 and 443 must be open to the BIG-IQ management address or any alternative address used to add the BIG-IP device to BIG-IQ Inventory

**BIG-IP Versions**

You can find the BIG-IQ compatibility matrix with BIG-IP releases at: https://support.f5.com/csp/article/K34133507

.. toctree::
   :maxdepth: 1
   :glob:

   lab*
