Lab 5.1: Create and deploy centralized Application Security policies
--------------------------------------------------------------------

.. note:: Make sure all the services are activated in your DCD

1. Log in to the BIG-IQ system with username (admin) and password (admin)

2. At the top of the screen, select Configuration from BIG-IQ menu

3. Expand the Security Column, then expand Web Application Security and then choose Policies

.. image:: ../pictures/module5/img_module5_lab1_1.png
  :align: center
  :scale: 50%

4. Select the policy named "templates-default" and click on "More / Clone".

.. image:: ../pictures/module5/img_module5_lab1_2.png
  :align: center
  :scale: 50%

- Name the new policy "CPB_Policy"

.. image:: ../pictures/module5/img_module5_lab1_3.png
  :align: center
  :scale: 50%

5. Click on *CPB_Policy* policy to open its parameters

- Expand the Policy Building section and click on *Settings*. Note the defaults and make sure that "Auto-Deploy Policy" is set to **Disabled**.

- Note that *Policy Building Mode* is defined to *Central*, it means that BIG-IP will send all the suggestions done by policy builder to BIG-IQ through BIG-IQ DCD component (Policy Building Device entry)

.. image:: ../pictures/module5/img_module5_lab1_4.png
  :align: center
  :scale: 50%

6. Now we will assign that new policy to the previously created Virtual Server.

- Go to **SECURITY -> Web Application Security / Virtual Servers** and filter search by "MyAppVS"

.. image:: ../pictures/module5/img_module5_lab1_5.png
  :align: center
  :scale: 50%

- Click on *MyAppVS5* from *BOS-vBIGIP01*

- In *Attached Policy*, choose "CPB_Policy" from the dropdown list

.. image:: ../pictures/module5/img_module5_lab1_6.png
  :align: center
  :scale: 50%

- Click "Save & Close"

7. Select both *"MyAppVS5"* from BOS-vBIGIP01 and BOS-vBIGIP02 and click *Deploy*

8. Name the new deployment as **Deploy WAF Policy**

.. image:: ../pictures/module5/img_module5_lab1_7.png
  :align: center
  :scale: 50%

9. At the bottom left of the menu you will see a Target Devices section, choose Find Relevant Devices

10. Move *BOS-vBIGIP01* and *BOS-vBIGIP02* in the *Selected* box and click **Create**

.. image:: ../pictures/module5/img_module5_lab1_8.png
  :align: center
  :scale: 50%

|

11. Note the evaluation process, when complete click on view to note the policy differences

12. Note also the view of the "Diff"

13. Deploy the changes. Choose the **Deploy Now** option and confirm

.. image:: ../pictures/module5/img_module5_lab1_9.png
  :align: center
  :scale: 50%

15. Validate successful completion by confirming that status is “Deployment Complete”

16. Log in to the BIG-IP BOS-vBIGIP01 (TMUI) with username (admin) and password (admin)

17. Expand the security tab and choose *Application Security -> Policy Building -> Traffic Learning*

- Note the status of Traffic Learning for policy *CPB_Policy*

.. image:: ../pictures/module5/img_module5_lab1_10.png
  :align: center
  :scale: 50%

18. Launch a SSH session to Ubuntu Lamp Server using your local SSH client and launch the following command:

- *# /home/f5/scripts/generate_bad_vs5.sh*
- Leave the script running in the background

19. Return to the BIG-IQ UI and navigate to Policy Building Suggestions of policy "CPB_Policy"

- You should see some suggestions appearing after few seconds
- Look for a learned action "Delete File Type" with violation 'illegal file type' with entity value *'exe'*

.. image:: ../pictures/module5/img_module5_lab1_11.png
  :align: center
  :scale: 50%

- Click on the "Delete File Type" link
- This will bring up a detailed suggestion menu. Choose Accept in the *Actions* button and confirm

.. image:: ../pictures/module5/img_module5_lab1_12.png
  :align: center
  :scale: 50%

20. Go back to *Policies -> CPB_Policy* - choose Deploy in the *More* button

.. image:: ../pictures/module5/img_module5_lab1_13.png
  :align: center
  :scale: 50%

21. Name the new deployment as **Deploy-WAF-suggestions** and deploy it immediately without an evaluation

.. image:: ../pictures/module5/img_module5_lab1_14.png
  :align: center
  :scale: 50%

22. At the bottom left of the menu you will see a Target Devices section, choose Find Relevant Devices

23. Move both BOS BIGIP in the *Selected* box, click **Deploy** and confirm Warning

.. image:: ../pictures/module5/img_module5_lab1_15.png
  :align: center
  :scale: 50%

24. Validate successful completion by confirming that status is “Deployment Complete”

.. image::  ../pictures/module5/img_module5_lab1_16.png
    :align: center
    :scale: 50%

|

That's it, you managed to create a central policy from BIG-IQ, assign the policy to a Virtual Server and deploy the policy.
You also learned how to view central suggestion from 'Learning Mode', accept the suggestion and deploy the modified policy.
