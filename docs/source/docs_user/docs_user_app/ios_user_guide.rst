.. _ios-user-guide:

=============================
iOS User Guide
=============================

App Access and Installation
----------------------------
You can download the mobile app (CANFISHPASS) from the `Apple App store <https://apps.apple.com/ca/app/canfishpass/id6749703687>`_. Once installed, the app will be accessible on your phone with the CWF logo as the app icon. 

.. figure:: img/apple_app_phone.png
    :align: center
    :width: 40%

You are now ready to open and explore the app!

App Overview and Guidance
----------------------------
This page contains information on:

- :ref:`Getting Started on the App <getting-started>`
- :ref:`A summary of the user interface components <interface>`
- :ref:`Navigating the map space and barrier symbology <navigation>`
- :ref:`Exploring barrier features <exploring-barriers>`
- :ref:`Assessing barrier features <assessing-barriers>`

.. _getting-started:

Getting Started
^^^^^^^^^^^^^^^^

Once the app is downloaded and installed, you can open it from your device’s home screen. When you first open the app you will be greeted with a home screen that has the CWF logo and a text box where you'll enter your email address and click 'Continue' which will bring you to the main app page and map space. Links to a Getting Started guide, Privacy Policy, and Terms of Use & Copyright are also available on this screen.

.. figure:: img/ios_email.png
    :align: center
    :width: 30%

.. _interface:

Interface Components
^^^^^^^^^^^^^^^^^^^^^^
Once you’ve passed the home screen, you’ll arrive at the main map interface. In the top-right corner, you’ll see six buttons/icons that give you access to key features of the app.

Here’s a quick summary of what each one does:

.. |logo| image:: img/arrow.png
   :width: 30pt
   :height: 30pt

.. |logo5| image:: img/homepage.png
   :width: 30pt
   :height: 30pt

.. |logo1| image:: img/settings.png
   :width: 30pt
   :height: 30pt

.. |logo2| image:: img/base_map.png
   :width: 30pt
   :height: 30pt

.. |logo3| image:: img/new_feature.png
   :width: 30pt
   :height: 30pt

.. |logo4| image:: img/legend.png
   :width: 30pt
   :height: 30pt

.. _my-location:

.. list-table:: Interface Components
   :widths: 25 25 50
   :header-rows: 1

   * - Button icon
     - Button Name 
     - Button Functionality

   * - |logo|
     - My Location
     - Snaps the map space back to your current location. 
    
   * - |logo5|
     - Homepage
     - Returns you to the homepage. 

   * - |logo1|
     - Profile 
     - Opens the Profile tab, within which you can request a password change, refresh map features and view/manage your cache of assessed features see :ref:`using the feature cache to upload saved assessment submissions for more information on the feature cache <feature-cache>`.

   * - |logo2|
     - Imagery/Base Map Toggle
     - Toggles between satellite imagery and base map views.

   * - |logo3|
     - New feature
     - Adds a new barrier feature point that does not already exist on the map, see :ref:`adding and assessing a new barrier below for more information on adding new features <adding-assessing-new-barriers>`. 
    
   * - |logo4|
     - Legend 
     - Opens the legend for features displayed on the map. 

.. figure:: img/ios_feature_map.png
    :align: center
    :width: 25%

.. _navigation:

Navigating the Map Space and Barrier Symbology
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

On the map space page, you should see your current location along with the default base map. If your location is not automatically displayed, ensure that your device’s location services are enabled and that the app has permission to access your location. Once permissions are confirmed, press the :ref:`My Location button <my-location>`. to find your current location on the map. 

You can navigate the map space using standard iOS gestures:

- Tap and drag to pan around the map.
- Pinch to zoom in or out.

If you zoom out too far on the map, barrier features will be hidden to improve app performance. As you zoom back in, they will reappear.

If this is your first time using the app, take a second to view some of the dams and stream crossings near your location.

You’ll also notice a small black crosshair at the center of the screen (see image below). This is the app cursor, which helps you select barrier points on the map. To select a barrier, simply drag the map until the crosshair aligns with the barrier of interest.

.. figure:: img/ios_update.png
    :align: center
    :width: 25%

Once the crosshair is aligned with a barrier point, an information box will appear at the bottom of the screen. This box displays the barrier ID, structure type, and passability status, along with ‘EXPLORE THIS FEATURE’ and ‘ASSESS THIS FEATURE’ buttons.

Dams are represented as squares, and stream crossings are represented as circles. The colour of each icon indicates the passability status. Use the legend button to identify what each colour means.

- Green - Passable 
- Orange - Partial Barrier
- Red - Barrier
- Purple - Unknown
- Dark Grey - N/A - No structure
- Light Grey - N/A - Decommissioned/Removed 

.. figure:: img/ios_features.png
    :align: center
    :width: 25%

Additionally, once you begin :ref:`assessing barriers <assessing-barriers>`, halos will appear around them to indicate their community status: 

- Dark Blue - Your Submitted Features
- Pink - Community Submitted Features
- Orange - Your Uploaded Features
- Light Blue - Your Autosaved Features
- Yellow - Your Not Uploaded Yet Features 

.. figure:: img/halo_barriers.png
    :align: center
    :width: 30%

.. _exploring-barriers:

Exploring Barriers
^^^^^^^^^^^^^^^^^^^

Once the crosshair is aligned with an existing barrier point, an information box will appear at the bottom of the screen with the structure type and passability status.

Click ‘EXPLORE THIS FEATURE’ to open the barrier information window.

.. figure:: img/exploring_barriers.png
    :align: center
    :width: 30%
    
This will display the existing information known about the structure from the Canadian Aquatic Barriers Database (CABD). You'll likely see lots of NULL values here - so any information you can provide helps us improve our database!

.. _assessing-barriers:

Assessing Barriers
^^^^^^^^^^^^^^^^^^^

All dams and stream crossings displayed in the map space are sourced from the Canadian Aquatic Barriers Database (CABD). With this app, you can either:

- Assess an existing barrier, or
- Create a new barrier feature that does not yet exist in the CABD.

To begin, align the app cursor with an existing barrier point, or move it to the location where you'd like to add a new barrier.

**Assessing Existing Barriers**

Once the crosshair is aligned with an existing barrier point, an information box will appear at the bottom of the screen with the structure type and passability status.

Click ‘ASSESS THIS FEATURE’ to open the assessment form.

Tip: If you're unsure what a question is asking, or how to respond, tap the Info icon at the top right of the question for additional details. 

.. raw:: html

    <video controls width="600"><source src="../../_static/ios_assess_existing.mp4"></video>

The first question will ask, “This structure is currently identified as (either a dam or a stream crossing), is this correct?""

- If the default structure type is correct, simply tap ‘Yes’ to proceed.
- If the structure type is incorrect, then tap ‘No’ if you know what structure type it is, or ‘Unsure’ in all other cases.

Next, indicate if you are able to access the site for further assessment. If you can't access the site, you will be able to submit your assessment after choosing a reason why the site can't be accessed.

If you can access the site, an additional set of assessment questions and photo prompts specific to that structure type or accessibility status will appear. Note that all questions must be filled out to save and submit your assessment.

.. _adding-assessing-new-barriers:

**Adding and Assessing a New Barrier**

If you find a dam or stream crossing that is not shown on the map (i.e., not already in the CABD), you can add a new feature and complete an assessment for it.

To add a new feature:

#. Use the ‘Go to Your Location’ button if you're physically at the structure site, or manually drag the crosshair to the correct location on the map.
#. Once the crosshair is at the appropriate spot, tap the plus sign button in the app menu. This will open the rapid assessment form.

.. raw:: html

    <video controls width="600"><source src="../../_static/ios_assess_new.mp4"></video>

Once you select the structure type, additional assessment questions and photo prompts will appear. 

Once a new barrier assessment has been saved or uploaded, a black feature point will appear on the map at the assessment location — a square for dams and a circle for stream crossings.
.. figure:: img/ios_new_features.png
    :align: center
    :width: 50%

.. _saving-uploading-assessments:

**Saving and Uploading Barrier Assessment Submissions**

Once you’ve completed all the questions in the assessment form, you’re ready to save or upload your assessment. At the bottom of the form, you’ll see four buttons: 'Save for Later', 'Upload', 'Delete' and 'Cancel'. 

.. figure:: img/ios_bottom.png
    :align: center
    :width: 40%

Clicking ‘SAVE’ will store the assessment locally on your device so that you can upload it later. The ‘SAVE’ function works whether you’re online or offline, including when connected to Wi-Fi, using cellular data, or with no service at all.

When an assessment is saved, the associated feature point will appear on the map with a yellow halo. You can reopen a saved form at any time to review or edit the content before choosing to either save it again or upload it. 

Clicking ‘UPLOAD’ will both save and immediately upload the completed assessment to the database. Once uploaded, the feature point will be displayed on the map with a green halo. You can open and review the content of an uploaded assessment, but you cannot edit it after it has been submitted. The ‘UPLOAD’ button appears blue when you have a Wi-Fi or cellular connection and is greyed out when offline. You can only upload assessments when you are connected to the internet. If you're offline, use the ‘SAVE’ button instead and upload your completed assessments once a connection is available.

**Using the Feature Cache to Upload Saved Assessment Submissions**
If you have multiple saved assessments that you want to upload all at once, open the Profile window at the top right of your screen. You’ll see a summary of the features you’ve already uploaded, as well as a list of saved assessments that are still waiting to be uploaded. 

While in this window, you can tap the ‘UPLOAD FEATURES’ button to submit all saved assessments at once. Once the upload is complete, the counts of saved assessments will be reset to zero.

.. figure:: img/ios_profile_screen.png
    :align: center
    :width: 50%

You will also see a  ‘DELETE ALL’ button on this screen. This button will remove all assessment data saved locally in the app, but will NOT delete any information from the CWF database.

The ‘DELETE ALL’ button is intended to help clear the app’s memory if performance becomes sluggish due to a large number of saved or uploaded features. You should only use this button if you are experiencing app performance issues, and it is essential to ensure that all saved features have been uploaded from the feature cache before doing so to avoid losing any unsubmitted data.