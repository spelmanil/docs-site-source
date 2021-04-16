# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.


Where is this??

<div style="width:170px; height:170px; margin:auto">
        <style type="text/css">
            
        .il_icon {
            width: 36px;
        }
        
        /* The icon width (set in .il_icon) is set to 36.
         The original icons had a width of 20.  This
         increase of 16 needs to be reflected in a number of places.
         - In .logo-container and .img-container and .icons-container,
         the width and height is changed from from 144 to 160.
         (not sure this is required for .img-container)
         - In .icon-box, the width is changed from 72 to 80.  The
         height is changed from 20 to 36.  The top is calculated
         as width-height.  Previsously, this was set to 52 (72-20).
         It is now set to 44 (80-36).
         - width and height in both .icon-inner and .icon are set to
         36 (previously 20).
         - width in .il_icon is set to 36.
         */

        .foot_bar {
            border-radius: 0px;
            xbackground: #f0f0f0;
            padding: 10px;
            

          
        }
        
        .img-container {
            width: 144px;
            height: 144px;
            position: relative;
            xborder-radius: 100rem;
            xdisplay: flex;
            align-items: center;
            justify-content: center;
            margin-left: auto;
            margin-right: auto;
            display: block        }
        
        .logo-container {
            width: 144px;
            height: 144px;
            xbackground: lightgreen;
            position: absolute;
            top: 0px;
            left: 0px;
            display: flex;
            align-items: center;
            justify-content: center
        }
        
        .icons-container {
            width: 144px;
            height: 144px;
            xbackground: pink;
            position: absolute;
            top: 0px;
            left: 0px
        }
        

        .icons-container {
            animation: rotate 30s linear infinite;
            transform-origin: center
        }
        
        .icon-box {
            width: 72px;
            height: 36px;
            transform-origin: bottom right;
            position: absolute;
            top: 36px
        }
         
        .icon-inner {
            width: 36px;
            height: 36px
        }
        
        .xicon {
            background-size: cover;
            width: 36px;
            height: 36px;
            animation: rotate 30s linear reverse infinite
        }
        

        .icon-box-1 {
            transform: rotate(0)
        }
        
        .icon-box-2 {
            transform: rotate(45deg)
        }
        
        .icon-inner-2 {
            transform: rotateZ(-45deg)
        }
        
        .icon-box-3 {
            transform: rotate(90deg)
        }
        
        .icon-inner-3 {
            transform: rotateZ(-90deg)
        }
        
        .icon-box-4 {
            transform: rotate(135deg)
        }
        
        .icon-inner-4 {
            transform: rotateZ(-135deg)
        }
        
        .icon-box-5 {
            transform: rotate(180deg)
        }
        
        .icon-inner-5 {
            transform: rotateZ(-180deg)
        }
        
        .icon-box-6 {
            transform: rotate(225deg)
        }
        
        .icon-inner-6 {
            transform: rotateZ(-225deg)
        }
        
        .icon-box-7 {
            transform: rotate(270deg)
        }
        
        .icon-inner-7 {
            transform: rotateZ(-270deg)
        }
        
        .icon-box-8 {
            transform: rotate(315deg)
        }
        
        .icon-inner-8 {
            transform: rotateZ(-315deg)
        }
        
        
       
       
        @keyframes spin {
            0% {
                transform: rotateY(-90deg)
            }
            100% {
                transform: rotateY(90deg)
            }
        }
        
        @keyframes spin-begin {
            0% {
                transform: rotateY(0)
            }
            10% {
                transform: rotateY(90deg)
            }
            90% {
                transform: rotateY(90deg)
            }
            100% {
                transform: rotateY(0)
            }
        }
        
        @keyframes rotate {
            0% {
                transform: rotateZ(0)
            }
            100% {
                transform: rotateZ(360deg)
            }
        }
        

        </style>


        <div class="foot_bar" data-module-index="0">
            <div class="img-container">
                
                <div class="logo-container">
                    <img src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_00.png" width="64"></img>
                </div>
                
                <div class="icons-container">
                    <div class="icon-box icon-box-1">
                        <div class="icon-inner icon-inner-1">
                            <div class="xicon icon-1">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_01.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-2">
                        <div class="icon-inner icon-inner-2">
                            <div class="xicon icon-2">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_02.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-3">
                        <div class="icon-inner icon-inner-3">
                            <div class="xicon icon-3">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_03.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-4">
                        <div class="icon-inner icon-inner-4">
                            <div class="xicon icon-4">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_04.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-5">
                        <div class="icon-inner icon-inner-5">
                            <div class="xicon icon-5">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_05.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-6">
                        <div class="icon-inner icon-inner-6">
                            <div class="xicon icon-6">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_06.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-7">
                        <div class="icon-inner icon-inner-7">
                            <div class="xicon icon-7">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_07.png"></img>
                            </div>
                        </div>
                    </div>
                    <div class="icon-box icon-box-8">
                        <div class="icon-inner icon-inner-8">
                            <div class="xicon icon-8">
                                <img class="il_icon" src="https://github.com/jvolcy/il_web_assets/raw/main/il_icons/icon_08.png"></img>
                            </div>
                        </div>
                    </div>

                </div>
            </div>
        </div>
</div>


Where does this show up??