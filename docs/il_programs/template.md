<link rel="stylesheet" href="../../css/images.css" />

Template for creating a new Google Doc page
==============================================

<!----------------- BEGIN: CUT HERE ----------------->


###[&#x1F4D8;Example Link](https://docs.google.com/document/d/e/2PACX-1vRNGVmAPAoiw89Ijf390RDFWfXwrnPF69wNq_8AQg1PtX-1PVroe0jQDRz29yZ3CuUOMscU-sRZQ5DF/pub?embedded=true)

<!-- Template 
###[&#x1F4D8;Name](GoogleLink?embedded=true)
-->

Append `?embedded=true` to the link provided when the Google page is published.

<hr>

Begin with a copy of this file.  Name it appropriately.  Then, create a directory to hold the media associated with the new page.  For consistency, give the directory the same name as your newly created md file.  So, for `template.md`, the directory will be `template`.  Place `template.md` on the root directory (the directory that contains the top-level index.md file.  Add an entry to `mkdocs.yml` that points to your .md file.

Assume we have an image `image1.jpg`.  Put this image in the `template` directory.  Reference the image with a local path `template\image1.jpg` in the following way:

```
![Alt text](template/image1.jpg?style=center50)
```

![Cute Baby](template/image1.jpg?style=center50)

The `Alt text` can be empty.  The style has values like `center50`, `right30`, `left10`, `scale70`, etc.  For these examples, the respective results would be "image is centered and scaled at 50%", "image is right-aligned and scaled at 30%", "image is left aligned and scaled at 10%" and "image is scaled at 70%".
*Note that in order to use these image style values, you must link to the appropriate css file at the top of your md file:*

```
<link rel="stylesheet" href="../css/images.css" />
```

!!! warning
    This is a warning for you.

!!! note
    This is a note for you.

!!! danger
    This is a danger notice for you.

!!! important
    This is an important message for you.


A few interesting Unicodes:  

RED APPLE: &#x1F34E;  
GREEN APPLE: &#x1F34F;  
BLUE HEART: &#x1F499;  
GREEN HEART: &#x1F49A;  
YELLOW HEART: &#x1F49B;  
PURPLE HEART: &#x1F49C;  
GREEN BOOK: &#x1F4D7;  
BLUE BOOK: &#x1F4D8;  
ORANGE BOOK: &#x1F4D9;  
LARGE RED CIRCLE: &#x1F534;  
LARGE BLUE CIRCLE: &#x1F535;  
LARGE ORANGE DIAMOND: &#x1F536;  
LARGE BLUE DIAMOND: &#x1F537;  
SMALL ORANGE DIAMOND: &#x1F538;  
SMALL BLUE DIAMOND: &#x1F539;  
UP-POINTING RED TRIANGLE: &#x1F53A;  
DOWN-POINTING RED TRIANGLE: &#x1F53B;  
UP-POINTING SMALL RED TRIANGLE: &#x1F53C;  
DOWN-POINTING SMALL RED TRIANGLE: &#x1F53D;  

<!----------------- END: CUT HERE ----------------->

<br><hr>

![](../images/il_logo.png?style=center20)
