<link rel="stylesheet" href="../css/images.css" />

&#x1F4D8; Mixamo Characters and Animations
==========================================

This is a 2-part guide.  It covers how to download humanoid characters and animations from the website mixamo.com.  I believe all the mixamo characters are humanoid, meaning that they are all _rigged_ in the same way.


<div style="background-color:lightblue; padding:20px">
<i><b>Skeletal animation</b></i> or <i><b>rigging</b></i> is a technique in computer animation in which a character (or other articulated object) is represented in two parts: a surface representation used to draw the character, called the <i>mesh</i> or <i>skin</i> and a hierarchical set of interconnected parts called <i>bones</i>, <i>skeleton</i> or <i>rig</i>.
<br/><br/>
<a href=https://en.wikipedia.org/wiki/Skeletal_animation>https://en.wikipedia.org/wiki/Skeletal_animation</a>

</div>

We will download characters and animations separately.  That way, we can download our characters one time, then apply any future animation we want to that character.

I recommend creating a mixamo folder somewhere on your hard drive to store your character, if you want to use the same character in multiple projects.  This folder should be outside of any Unity project.  Give it any name you choose.  Assets stored here will be project independent.  We will refer to this folder as your “mixamo folder”.  Tip: You will want to organize this folder into sub-folders by character and animation.



Downloading a Character From Mixamo
-----------------------------------


###Step 1: Download your character



*   Go to mixamo.com.  Login.
*   Select the character you wish to download.
*   Unselect all animations on the character.  Your character should be in the T position.
*   Click “Download”.  Your download options should include only “Format” and “Pose”.  If you see options for “Frames per Second”, “Skin” or “Keyframe Reduction”, you have an associated animation with your character.


![](mixamo_characters_and_animations/Figure1.png?style=center80)

![](mixamo_characters_and_animations/Figure2.png?style=center80)



*   Select “FBX for Unity” for the Format.  “T-Pose” should be selected for the Pose.
*   Save the .FBX file to your mixamo folder

###Step 2: Set your character’s rig to humanoid



*   Import your character from Step 1 into Unity.  If your character’s color does not load properly, select the character asset (not the instance) and click on “Extract Textures” under the Materials tab in the Inspector window.  When prompted, store the extracted textures (image files) to a subfolder named “Textures”.  You can create this folder before extracting or at the time of extraction.  See “[Mixamo Textures MIA](https://docs.google.com/document/d/18OPkZ1yDrwqq3VgQA17xtdnw_1w5aVq7z8JeZwEobE8/edit?usp=sharing)” for more details.

![](mixamo_characters_and_animations/Figure3.png?style=center60)

*   Select the character.  In the Inspector window, select the “Rig” tab and set the “Animation Type” to “Humanoid”.  Click “Apply”.  See the figure below.

![](mixamo_characters_and_animations/Figure4.png?style=center60)

---

**Extra steps for “scary” models**

At times, your imported model may not look right.  In these cases, the most notable oddity are the eye sockets.  See the example below.


![](mixamo_characters_and_animations/scary_model.png?style=center50)

Pretty scary, Huh?  This is an issue with the default material shader.  As you can see, the shader is “Transparent”, allowing us to see through parts of the model.  In the image above, we see the eye sockets, and the lower jaw through the model’s skin.  If you run into this type of issue, refer to the [Mixamo Model Texture & Shading Problems](href="https://docs.google.com/document/d/1yGQLLVB1-6Ytr1VPS8eV7kL3AcsWXV6DAeS0_haazRg/edit?usp=sharing) guide.

<br/>


Downloading Animations From Mixamo
----------------------------------

###Step 3: Download an Animation


*   Go to mixamo.com and select any character.  “X Bot” or “Y Bot” are recommended for this purpose because they generate smaller download files.  The character is just a carrier for the animation we want to acquire and will eventually be discarded.


![](mixamo_characters_and_animations/bots.png?style=center60)



*   Select the animation you wish to download
*   If the animation has a _root transform_, you will see an “In Place” checkbox as part of the animation option.  If unsure, select this as shown in the image below.  A root transform causes the animation to automatically translate during the course of the animation.  For example, a root transformation would cause walking animation to actually travel.  Selecting “In Place” causes the animation to cycle without displacing the character.  This is probably the behavior you want.


![](mixamo_characters_and_animations/check_in_place.png?style=center50)


*   Click download.  4 download options should present themselves (see the figure below).  Select “FBX for Unity” for the Format.  Select 30 for the Frames per Second.  Higher frame rates will result in smoother animations at the cost of larger files.  Set “Keyframe Reduction” to None.  Set the “Skin” to “without skin”.  We are interested in the animation only.  Omitting the skin will result in a much reduced download size.


![](mixamo_characters_and_animations/Figure8.png?style=center80)


*   Save the .FBX file in your mixamo folder
*   Repeat Step 3 for each animation you want to download

###Step 4: Extract the animation from the FBX file



*   Import your animation from Step 3 into Unity.  Note that the FBX contains only a rig and an animation asset (no character) as shown below.

![](mixamo_characters_and_animations/fbx_file_content.png?style=center50)

*   Select the top-level asset and once more, set the Rig type to “Humanoid” and click Apply.


![](mixamo_characters_and_animations/Figure4.png?style=center60)


*   Your imported asset should now contain a humanoid avatar.  See the image below.

![](mixamo_characters_and_animations/fbx_create_avatar.png?style=center60)


*   We can now extract the animation and discard this FBX file.  This will reduce the size of our project.  To do this, select the animation (the animation only, not the entire asset) and click ⌘-D (or Ctrl-D on a Windows machine) to “duplicate” the animation.  Note that you must set the rig to humanoid before duplicating the animation for the animation to work with other humanoid avatars.

![](mixamo_characters_and_animations/fbx_duplicate_anim.png?style=center80)


*   Now, delete the entire imported asset, leaving only the duplicated animation.  This animation can now be applied to any humanoid asset.

![](mixamo_characters_and_animations/fbx_select_and_delete.png?style=center80)

*   In your project folder, there should be a newly created .anim file.  If your animation was a walking animation, for example, this file might be called walking.anim.  You can save a copy of this file in your mixamo folder.  It can be imported into future Unity projects and used with any other humanoid character.  (Hint: right-clicking on the animation allows you to “Reveal in Finder”).

###Step 5: Apply the animation to the character



*   Instantiate the character asset from Part I to create a GameObject instance in the project window.
*   We can apply our animation to any humanoid character by simply dragging and dropping it onto an instantiated humanoid character in the project window.
*   Note that if you apply the animation to a character before you set the character rig to “humanoid”, you will have to attach the avatar to the animator manually.  This is shown below.  In other words, when you apply the animation to a humanoid character, an Animator is created and a reference to the character’s avatar is automatically set in the animator.  If you apply the animation to a non-humanoid character (or a character whose rig you haven’t already set to “humanoid”), then the automatic association to the character’s humanoid avatar is not set.  You will have to set it manually after to change the character’s rig to “humanoid”.

![](mixamo_characters_and_animations/fbx_set_avatar.png?style=center60)

Select the instance of the character asset in the Hierarchy window to bring up the character inspector.



<br><hr>

![](images/il_logo.png?style=center20)
