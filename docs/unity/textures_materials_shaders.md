<link rel="stylesheet" href="../../css/images.css" />

&#x1F4D8; Understanding Textures, Materials and Shaders
==============================================
Unity makes extensive use of regular image files (.jpeg, .png, .bmp, etc.).  When image files are used as 2D images, they are called ***sprites***.  When image files are used to wrap 3D objects, they are called ***textures***.

| | |
|:---:|:---:|
|![](./textures_materials_shaders/book_sprite.png?style=center80)|<br/></br>a JPEG image used as a ***sprite***|
|![](./textures_materials_shaders/book_texture.png?style=center90)|<br/></br>same image used as a ***texture***|

Knowing the color of an object is not enough to produce a realistic rendering of that object.  Real objects have surface roughness, can be specular or diffuse, can be metallic, may glow and have other properties that affect how they appear.  In Unity, ***materials*** are created to capture the texture as well as other parameters needed to fully describe how an object will look.

You *cannot* apply a texture to an object.  If you could, this would be the result:
![](./textures_materials_shaders/no_material.png?style=center100)

Not a realistic rendering, Huh?  What this is is basically a "colored-in" mesh.  What, in fact, we want looks more like this:  

![](./textures_materials_shaders/material_shading.png?style=center40)

This object is the result of applying a *material* to the same object.  A *material* consists of an object's texture and its surface information.

!!! Tip
    ***material*** ** = Texture + Surface Information**

Here is a simple texture: 
![](./textures_materials_shaders/red.png?style=center20)

Here are examples of materials all created from this simple texture:  

![](./textures_materials_shaders/materials.png?style=center100)

Notice how different these materials look compared to the texture from which they were created.  3-D objects are “skinned” with materials, not textures.  You cannot apply a texture directly to a 3D object, because textures carry no surface information.  To wrap a 3D object in a texture, first create a material from the texture.  Then apply the material to the object.

Even given a material that properly describes an object's surface, we are still unable to generate a realistic rendering of the object on screen.  Doing that depends not only on the object's surface property, but also on the lighting condition and viewing angle.  Objects will look different under different color lights.  They will look different under a diffuse (think cloudy day) light versus under direct illumination.  It is the role of the ***shader*** to properly render an object on the sceen in real-time.  *Shaders* are code scripts that, given an object's shape, its material, the viewing angle and the lighting conditions, compute how to render the object on the screen.

![](./textures_materials_shaders/shader.png?style=center100)



<br><hr>

![](../images/il_logo.png?style=center20)
