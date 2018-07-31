Lab 5.1: Create and deploy centralized Application Security policies
--------------------------------------------------------------------

.. note:: Make sure all the services are activated in your DCD

1. Log in to the BIG-IQ system with username (admin) and password (admin)

2. At the top of the screen, select Configuration from BIG-IQ menu

3. Expand the Security Column, then expand Web Application Security and then choose Policies

.. image:: ../pictures/module5/img_module5_lab1_1.png
  :align: center
  :scale: 50%

4. Click on CPB_Policy policy to open its parameters

- Expand the Policy Building tab and click on settings. Note the defaults

.. image:: ../pictures/module5/img_module5_lab1_2.png
  :align: center
  :scale: 50%

5. Change the Policy Building Mode to Central. Accept the default value Auto-Select for the Policy Building Device and choose save.
Note which device is selected.

.. image:: ../pictures/module5/img_module5_lab1_3.png
  :align: center
  :scale: 50%

.. image:: ../pictures/module5/img_module5_lab1_4.png
  :align: center
  :scale: 50%

6. Log in to the BIG-IP 10.1.1.8 (TMUI) with your username (admin) and password (admin)

7. Expand the security tab and choose *Application Security -> Policy Building -> Traffic Learning*

- Note the status of Traffic Learning for CPB_Policy

.. image:: ../pictures/module5/img_module5_lab1_5.png
  :align: center
  :scale: 50%

8. Return to the BIG-IQ UI and navigate to Policy Building Suggestions

- Look for a learned file entity similar to hkr below
- Click on its associated Add File Type action
- This will bring up a detailed suggestion menu. Choose Accept and Stage and confirm

.. image:: ../pictures/module5/img_module5_lab1_6.png
  :align: center
  :scale: 50%

9. Notice that File Type hxr is now added to file types

.. image:: ../pictures/module5/img_module5_lab1_7.png
  :align: center
  :scale: 50%

10. Go back to *Policies -> CPB_Policy* - choose Deploy

11. Name the new deployment as **DeployCPBUpdate**

.. image:: ../pictures/module5/img_module5_lab1_8.png
  :align: center
  :scale: 50%

12. At the bottom left of the menu you will see a Target Devices section, choose Find Relevant Devices

.. image:: ../pictures/module5/img_module5_lab1_9.png
  :align: center
  :scale: 50%

13. Move 10.1.1.8 is the "Selected" box and click **Create**

.. image:: ../pictures/module5/img_module5_lab1_10.png
  :align: center
  :scale: 50%

14. Note the evaluation process, when complete click on view to note the policy differences

.. image:: ../pictures/module5/img_module5_lab1_11.png
  :align: center
  :scale: 50%

15. Note the view of the "Diff"

.. image:: ../pictures/module5/img_module5_lab1_12.png
  :align: center
  :scale: 50%

16. Click **Cancel** to return to the Evaluate and Deploy menu

17. Deploy the changes. Choose the **Deploy Now** option and confirm

.. image:: ../pictures/module5/img_module5_lab1_13.png
  :align: center
  :scale: 50%

18. Validate successful completion by confirming that status is “Deployment Complete”

.. image::  ../pictures/module5/img_module5_lab1_14.png
    :align: center
    :scale: 50%