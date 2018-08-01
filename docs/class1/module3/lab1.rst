Lab 3.1: ADC/LTM Management Workflow
------------------------------------

BIG-IQ is able to create nodes, monitors, pools, profiles, and virtual servers, so a user can create and stage a new application direct on the BIG-IQ. BIG-IQ can create some monitors and profiles on BIG-IQ and can associate other profiles and monitors that already exist on the managed BIG-IP.

1. Navigate to the Configuration tab on the top menu bar

2. We will build our application starting at the nodes and making our way to the virtual servers. Navigate to **LOCAL TRAFFIC > Nodes**

.. image:: ../pictures/module3/img_module3_lab1_1.png
  :align: center
  :scale: 50%

3. Click the Create button to create a node

4. Fill out the configuration properties for the node

- Name: MyAppNode5
- Device: BOS-vBIGIP01.termmarc.com
- Address: 10.1.10.120

.. image:: ../pictures/module3/img_module3_lab1_2.png
  :align: center
  :scale: 50%

5. Click the Save & Close button in the lower right

6. Repeat steps 4 and 5 for the second node

- Name: MyAppNode6
- Device: BOS-vBIGIP01.termmarc.com
- Address: 10.1.10.121

7. Verify that the MyApp nodes are created by typing MyApp in the filter box in the upper right and pressing return

8. You should now see an entry for each of the MyApp nodes on both BOS BIG-IPs.

.. image:: ../pictures/module3/img_module3_lab1_3.png
  :align: center
  :scale: 50%

.. note:: When you create an object on a clustered device, BIG-IQ automatically replicates that configuration to the peer node in the staged configuration.

9. Now we will create a pool with these nodes as pool members. Navigate to **LOCAL TRAFFIC > Pools**

.. image:: ../pictures/module3/img_module3_lab1_4.png
  :align: center
  :scale: 50%

10. Click the Create button to start creating your pool

11. Fill out the Pool Properties

- Name: MyAppPool5
- Device: BOS-vBIGIP01.termmarc.com
- Health Monitors: /Common/tcp
- Load Balancing Method: Round Robin

.. image:: ../pictures/module3/img_module3_lab1_5.png
  :align: center
  :scale: 50%

12. Click the Save & Close button in the lower right

13. Click on the MyAppPool5 name in the list of pools to add pool members

14. Click on the New Member button under Resources to add pool members

15. Complete the Pool Member Properties for the first pool member

- Node Type: Existing Node
- Node: MyAppNode5
- Port: 80 - HTTP

.. image:: ../pictures/module3/img_module3_lab1_6.png
  :align: center
  :scale: 50%

16. Click the Save button in the lower right to save the pool member

17. Repeat steps 14 and 15 for the second pool member

18. Click the Save & Close button in the lower right to save your pool

19. Now we will create a custom profile for our Virtual Server. Navigate to **LOCAL TRAFFIC > Profiles**

.. image:: ../pictures/module3/img_module3_lab1_7.png
  :align: center
  :scale: 50%

20. Click the Create button to create our custom profile

21. Fill out the Profile Properties

- Name: Source_Addr_Timeout_75
- Type: Persistence Source Address
- Parent Profile: source_addr
- Timeout: Specify 75 seconds

.. image:: ../pictures/module3/img_module3_lab1_8.png
  :align: center
  :scale: 50%

22. Click Save & Close in the lower right

23. Now we will create our Virtual Server. Navigate to **LOCAL TRAFFIC > Virtual Servers**

.. image:: ../pictures/module3/img_module3_lab1_9.png
  :align: center
  :scale: 50%

24. Click the Create button to create the Virtual Server

25. Fill out the Virtual Server Properties

- Name: MyAppVS5
- Device: BOS-vBIGIP01.termmarc.com
- Destination Address: 10.1.10.210
- Service Port 8088
- HTTP Profile: http

.. image:: ../pictures/module3/img_module3_lab1_10.png
  :align: center
  :scale: 50%

26. Scroll down and fill out the Resources

- Default Pool: MyAppPool
- Default Persistence Profile: Source_Addr_Timeout_75

Leave all other options at their default settings

.. image:: ../pictures/module3/img_module3_lab1_11.png
  :align: center
  :scale: 50%

27. Click Save & Close in the lower right

28. We now have staged our application and we will deploy it in a later workflow
