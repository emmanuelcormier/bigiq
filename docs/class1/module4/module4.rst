Module 4: BIG-IQ License Management
===================================

In this module, we will learn how to manage BIG-IP licenses from BIG-IQ.

BIG-IQ can manage licenses for up to 5000 BIG-IP VEs.

There are 3 ways that BIG-IQ can give a license to a BIG-IP:

- Managed devices: If a device is already managed by BIG-IQ, you can select the device from a list
- Unmanaged devices: If you don’t want to manage the device with BIG-IQ, you just want to give it a license, you can specify IP, port, username, and password to push a license to a device
- Disconnected Devices: [NEW from 5.4] For situations where the BIG-IQ cannot talk directly to the BIG-IP, you can provide device MAC address and hypervisor information to BIG-IQ via the API and BIG-IQ will return a license that can be copied on to the box via some intermediary orchestrator

BIG-IQ can handle various types of pool licenses, including subscription and ELA pools, as well as allowing the customer to create their own pool of licenses out of individual VE keys.

.. toctree::
   :maxdepth: 1
   :glob:

   lab*
