<link rel="stylesheet" href="../../css/images.css" />

&#x1F4D8; Instructions for creating a simple 1d animation blend in Unity
========================================================================

Animation blends in Unity are created using blend trees.

!!! note
    Blend Trees are used for allowing multiple animations to be blended smoothly by incorporating parts of them all to varying degrees. The amount that each of the motions contributes to the final effect is controlled using a blending parameter.  In order for the blended motion to make sense, the motions that are blended must be of similar (not identical) in nature and timing.

    [https://docs.unity3d.com/Manual/class-BlendTree.html](https://docs.unity3d.com/Manual/class-BlendTree.html)

Begin with a downloaded character and 2 animations to be blended.  For this example, we use the ybot character with “Standard Walk” and “Injured Walk” animations.  We will create a blending parameter named injury which is a float that can take values from 0.0 to 1.0 inclusive.  When injury is 0.0, the character should execute the “Standard Walk” animation.  When injury is 1.0, the character should execute the “Injured Walk” animation.  For values of injury between 0.0 and 1.0, the character should execute a proportional blend of the 2 animations.

##Single, 1D Blend Tree
**Step 1: Create Animator Controller**

*   Into an empty Unity 3D project, import the character asset and the 2 animations to be blended.  Add the character to the scene (instantiate the character).  Be sure the character asset’s rig is set to “humanoid”.
*   Drag an animation to the instantiated character in the Hierarchy window to create an animation controller for the character.
*   Alternatively, in the “Assets” window, right click the character asset and “Create->Animator Controller”.  Name the controller appropriately.  Then associate the controller with the instantiated character.  See the figure below.  You can then add the 2 animations to the controller.


|  |
| :--- |
|![](1d_animation_blends/step1.png?style=left60)<br/><br/>If you manually create the animator controller, you will need to associate it with the character through the character inspector.|

<br/>

**Step 2: Create a Blend Tree**

*   Create a blend tree in the Animator as shown in the figure below.  Set it as the default state.


![](1d_animation_blends/step2ab.png?style=center100)

<br/>

|  |
| :--- |
|![](1d_animation_blends/step2c.png?style=right60)<br/><br/>Create a blending parameter by navigating to the Parameters window of the Animator and selecting “Float” from the drop down menu as shown.  Create a parameter named “injury”.  Then, delete the default “Blend” parameter if it is present.|

<br/>

**Step 3: Add Animations to the Blend Tree**

|  |
| :--- |
|![](1d_animation_blends/step3a.png?style=right50)<br/><br/>Double click on the blend tree in the base layer window to bring up the blend tree editor.  You should see the blend parameter and a slide control.  Right-click on the Blend Tree and select “Add Motion” to add our first motion to be blended.|

<br/>

|  |
| :--- |
|![](1d_animation_blends/step3b.png?style=right60)<br/><br/>Add the “Standard Walk” motion.|

<br/>

|  |
| :--- |
|![](1d_animation_blends/step3c.png?style=right50)<br/><br/>Repeat the last 2 steps to add the “Injured Walk” motion.|

<br/>

*   You should now be able to execute the project and observe the blended animation.  Change the value of the injury blend parameter to verify that you can smoothly transition from one animation to the other.  If your blended animation does not loop properly, make sure that both animations have the “Loop Time” option checked.

<br/>

##Adding Transition States to/from the Blend Trees

**Step 4: Add the Individual Animations **


|  |
| :--- | 
|![](1d_animation_blends/step4a.png?style=right60)<br/><br/>Add the “Standard Walk” and “Injured Walk” animations to the base layout and set the “Standard Walk” animation as the default state.|

<br/>

|  |
| :--- | 
|![](1d_animation_blends/step4b.png?style=right60)<br/><br/>Now create transitions to and from the blend state as shown.  We want to configure the animations in the following way:  for values of injury &lt; 0.1, we should be in the “Standard Walk” state.  For values of injury > 0.9, we should be in the “Injury Walk” state.  For values of injury between 0.1 and 0.9, we should be in the blend state.|

<br/>

|  |
| :--- | 
|![](1d_animation_blends/step4c.png?style=right60)<br/><br/>Select the individual transitions for edit by clicking on its representative arrow.  In the image shown, the transition from “Standard Walk” to the blend tree is set to “injury > 0.1”.<br/><br/>Repeat a similar process for the other 3 transitions.|

<br/>

*   You should now be able to see the animation transition between “Standard Walk”, “Injured Walk” and the blend tree as the value of injury changes.

<br/>

**Step 5: Keyboard controls **



*   You can use keyboard inputs to change the value of injury at runtime.  Create a script (called SetInjury in this example) and associate it with the character.  Here is the contents of the script:

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
 
public class SetInjury : MonoBehaviour
{
    Animator animator;
    const float injuryInc = 0.01f;
 
    // Start is called before the first frame update
    void Start()
    {
        animator = GetComponent<Animator>();
    }
 
    // Update is called once per frame
    void Update()
    {
 
        if (Input.GetKey(KeyCode.RightArrow))
        {
            float injury = animator.GetFloat("injury");
            injury = injury + injuryInc;
            if (injury > 1.0f) injury = 1.0f;
            animator.SetFloat("injury", injury);
        }
 
        if (Input.GetKey(KeyCode.LeftArrow))
        {
            float injury = animator.GetFloat("injury");
            injury = injury - injuryInc;
            if (injury < 0.0f) injury = 0.0f;
            animator.SetFloat("injury", injury);
        }
    }
}


```


<br><hr>

![](../images/il_logo.png?style=center20)
