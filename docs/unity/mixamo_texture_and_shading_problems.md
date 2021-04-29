<link rel="stylesheet" href="../../css/images.css" />

&#x1F4D8; Mixamo Model Texture & Shading Problems
=================================================



### Extra steps for “funky” models

At times, your imported model may not look right.  In these cases, the most notable oddity are the eye sockets.  Here is an example:



![](mixamo_texture_and_shading_problems/caseB.png?style=center60)



Pretty scary, Huh?  This is an issue with the default material shader.  As you can see, the shader is “Transparent”, allowing us to see through parts of the model.  In the image above, we see the eye sockets, and the lower jaw through the model’s skin.

Another common problem is missing or unapplied textures.  Here is an example:

![](mixamo_texture_and_shading_problems/caseC.png?style=center60)

In this case, the shading is fine, but no texture has been applied to the model.

We can categorize texture and shading problems into 4 cases as shown below:



|  |  |
|:---:|:---:|
|**Case A<br/>improperly textured, improperly shaded**![](mixamo_texture_and_shading_problems/caseA.png?style=center80)|**Case B<br/>properly textured, improperly shaded**![](mixamo_texture_and_shading_problems/caseB.png?style=center80)|
|**Case C<br/>improperly textured, properly shaded**![](mixamo_texture_and_shading_problems/caseC.png?style=center80)|**Case D<br/>properly textured, properly shaded**![](mixamo_texture_and_shading_problems/caseD.png?style=center80)|

<br/><br/>

Case D above is a properly textured and shaded model.  This is what we hope to see when we import a model.  Case B is fairly common.  In this case, the model is properly textured (properly colored), but improperly shaded.  Some of the material shaders should be “opaque”, but are “transparent”.  Case C is also common.  Here, the model is properly shaded (opacities are correct), but no texture is applied.  Case A is the most difficult.  Here, the model is neither properly shaded nor textured.
<br/><br/>

### Addressing rendering issues

When confronted with a model with both shading and texturing problems (case A), begin by fixing the texturing problem.  In other words, go from A->B->D rather than A->C->D.
<br/></br/>

**Fixing texturing issues**

You can fix most texturing issues by following the instructions in the “[Instructions for fixing missing mixamo character textures](fixing_missing_textures.md)” guide.  Texturing issues are shown in Cases A and C above.
<br/><br/>

**Fixing Shading issues**

Shading issues are shown in Cases A and B above.  The fix is to change the shader rendering mode for each of the model’s materials from “Transparent” to  “Opaque”.  How we do this depends on whether or not your model is using materials that are external to the model file.

If your model was not textured on import, follow the direction above to get it textured.  In the process of fixing the texturing issue, you will have created an external copy of the model’s materials.  This is required to fix the shading issue.

If, on the other hand, your model was properly textured on import but has a shading problem (case B), then your model is  using embedded materials.  Unfortunately, we can’t change the shader for materials embedded in a prefab.  Instead, we have to make copies of the materials, adjust their shaders then re-assign the new materials to the model.  Follow the direction in the “[Instructions for fixing missing mixamo character textures](fixing_missing_textures.md)” guide to make an external copy of the model’s materials.


Once your materials are extracted, 

In the materials folder, select all materials

In the inspector, change the shader from Transparent to Opaque



??




<br><hr>

![](../images/il_logo.png?style=center20)
