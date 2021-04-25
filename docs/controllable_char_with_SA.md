<link rel="stylesheet" href="../css/images.css" />

&#x1F4D8; Creating Controllable Characters with Unity Standard Assets
=======================================================================

In this exercise, you will create a keyboard- and joystick-controllable third person character using the Unity Standard Assets.  This guide uses _Standard Assets 2018.4.1_ running on _Unity 2019.4.16f1 Personal_.

![](controllable_char_with_SA/image1.jpg?style=left25)

![](controllable_char_with_SA/image2.jpg?style=left25)

![](controllable_char_with_SA/image3.jpg?style=left25)

![](controllable_char_with_SA/image4.jpg?style=scale25)

Begin by downloading the character you want to use for this exercise.  Follow Steps 1 and 3 of the “_[Instructions for downloading characters and animations from mixamo.com](mixamo_characters_and_animations.md)_” guide to download your character.  You can also download characters from the Unity store or from other online sources.

This guide makes use of the Standard Assets (SA) package created by Unity and made available for free through the Unity Assets Store.  The SAs provide resources to quickly complete common tasks.  We will be using it to create a third-person character that you will be able to control with the keyboard or with a joystick.  This is a three part guide.  Do part I first.  You can do parts II or III in any order.

Part I - Create a 3rd Person Controller
---------------------------------------


1. Create a new 3D project
2. We will need two resources from the SA package: CrossPlatformInput and ThirdPersonCharacter
3. Navigate to the Asset Store:  
    `Window->Asset Store`  
    and search for the Unity Standard Assets.
4. Once you have the package, select “Import” to bring it into the current project.

    ![](controllable_char_with_SA/SA.png?style=center70)
    <br/>
5. You will be shown a menu of resources within the SA package available for import.  While you can import everything, this will result in a larger than necessary project directory (always be mindful of disk space when working with Unity).  For Part I of this guide, you need to import only 2 things: _ThirdPersonCharacter_ and _CrossPlatformInput_:  
    `   Standard Assets->CrossPlatformInput`  
    `   Standard Assets->Characters->ThirdPersonCharacter`  

    ![](controllable_char_with_SA/SA_select_packages.png?style=center70)

    !!! Tip
        For Part II, we will need the _Cameras_ resource.  You may want to import it now to save time later.

6. From the ThirdPersonCharacter folder, instantiate a ThirdPersonController by dragging the ThirdPersonController to the Hierarchy Window.
    (_Assets->StandardAssets->Characters->ThirdPersonCharacter->Prefabs->ThirdPersonController_)


    ![](controllable_char_with_SA/3rd_person_asset.png?style=center100)

    <br/>This will create the character “Ethan” that should be visible in the scene.  

7. If you run the project, you will notice that Ethan simply falls out of view.  This is because the character is subject to gravity.  To fix this, we need to create a floor.
8. Instantiate a cube.  Flatten and stretch it to create a floor.  For example, you might scale it in its transform window with the X and Z scales set to 100 and the Y scale set to 0.1.  However you scale it, position it so that it is immediately below Ethan’s feet.

    ![](controllable_char_with_SA/ethan.png?style=center60)
   <br/>
9. Now run the project again.  This time, Ethan has a floor beneath his feet.  You should be able to control him with the keyboard arrows or with a joystick.  Use ‘C’ to crouch down and use the spacebar to jump.  Use the left shift key to make him walk.

Part II - Add a 3rd Player Camera
---------------------------------

In this part, we will replace the default static camera with a 3rd player camera that will follow the player around.



1. If you hadn’t already done so in Step 5 of Part I, add a third SA asset to the project: Cameras (“Standard Assets->Cameras”)
2. Delete the “Main Camera” from the project hierarchy
3. Instantiate a “multipurpose camera rig” to the hierarchy.  From the Assets window, (_Assets->StandardAssets->Cameras->Prefabs->MultipuposeCameraRig_)
4. Tag the ThirdPersonController as the “Player” in the Inspector.  This is how the camera knows what to follow.

    ![](controllable_char_with_SA/3rd_person_select.png?style=center100)

   <br/>
5. Run the project again.  Note how the camera follows the player.  Feel free to experiment with the other available cameras.  Note that the first person camera requires importing _Standard Assets->Utility_.



Part III - Replace the Default Character
----------------------------------------

In this part, we will replace Ethan with a character of our choice.

1. Import a rigged humanoid character model into the project.  Be certain that your character’s Rig is set to “humanoid”.  For this example, we have imported a character named Louise who we will use to replace Ethan.
2. The ThirdPersonController is a prefab.  Think of it as a zip file that contains other files.  Just like you can’t modify the contents of a zip file without unzipping it, you can’t modify the contents of a prefab without “unpacking” it.  The Ethan character is contained inside the ThirdPersonController prefab.  In order to replace Ethan with Louise, we must unpack the prefab.  In the hierarchy window, right-click on the ThirdPersonController and select “Unpack Prefab”. <br/><br/>

    ![](controllable_char_with_SA/unpack_prefab.png?style=center50)
    <br/>

3.  Once the prefab is unpacked, instantiate a copy of Louise inside the unpacked prefab  
4.  Now, delete the 3 files (EthanBody, EthanModel, EthanSkeleton) that comprise the Ethan character.  
    <br/>

    |  |  |  |
    |:---:|:---:|:---:|
    |![](controllable_char_with_SA/louis_and_ethan_hierarchy.png?style=scale90) Step 3||![](controllable_char_with_SA/louise_hierarchy.png?style=scale90) Step 4|  

    <br/>

5. Finally, we need to tell the ThirdPersonController to use out new character model  
	 *  In the Inspector, for the ThirdPersonController, set the Animator Avatar to the avatar of the new character model.  
	 *  In the Inspector, for the new character model, assure that the Animator Controller is set to ‘None’ and that the model’s avatar is correctly set.  
   <br/>

    |  |  |  |
    |:---:|:---:|:---:|
    |![](controllable_char_with_SA/avatar.png?style=scale90)||![](controllable_char_with_SA/louise_avatar.png?style=scale90)|

    <br/>

6. You should now be able to run the project and control your new character.


<br><hr>

![](images/il_logo.png?style=center20)
