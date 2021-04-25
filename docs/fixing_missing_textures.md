<link rel="stylesheet" href="../css/images.css" />

&#x1F4D8; Instructions for fixing missing mixamo character textures
===================================================================

At times, your imported mixamo model may show no texture.  Here is an example:

![](fixing_missing_textures/image1.png?style=center60)

Rest assured: mixamo models have built-in textures!  (models from other sites may have external textures or no textures at all.  Those may require a different solution than the one presented here.)  
<br/>

**Step 1: Create a home for your model’s textures**

Create a folder named “Textures” in the same directory where the downloaded model is.  The folder must be named “Textures”.  You may rename and move it later, but by default, this is where Unity will look for textures for your model.

![](fixing_missing_textures/image2.png?style=center80)

<br/>
**Step 2: Extract your model’s textures**

Select the model in the “Assets” window (not its instance in the Hierarchy).  In the Inspector, select “Materials” then “Extract Textures”.   Then, when prompted, select the folder you created in step 1 as the destination for your extracted textures.

![](fixing_missing_textures/image3.png?style=center60)

![](fixing_missing_textures/image4.png?style=center60)

If everything went right, your model should now be properly textured.  If a dialog box pops up warning you of unmarked textures used as normal maps, simply accept the recommended changes by selecting “Fix now”.
    
![](fixing_missing_textures/image5.png?style=center70)

<br><hr>

![](images/il_logo.png?style=center20)
