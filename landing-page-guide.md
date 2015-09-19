### Landing Page Guide

#### Basic rules

1. HTML5
1. All elements of the template must be in absolute position with top and left in pixels
1. CSS file must define colors for: a, a:hover
1. It is forbidden to use: padding, margin, letter-spacing, white-space
1. Data-editable must specify: top left width height [background : color, image, position, repeat ...] [border] [border-radius] box-shadow opacity
1. Line-height must be set in %
1. Any element that can be edited, must have a set height and width
1. The template must have a main css file called: style.css. This file must specify that the style cannot be set inline.
1. Styles should be set inline when possible
1. Styles for links should not be grouped
1. Style for the background image should not be set for the whole body
1. Every section must be set to 100% and have set height
1. Font weight should be set in numbers only
1. In case of the use of a background image: linear-gradient() it should be left in a solid background color for older browser compatibility

#### Folder structure and main template

Folder structure is located in landing-page/example-folder-structure

Base html template for landing page:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>title</title>
    <meta charset="utf-8"/>
    <meta name="keywords" content="meta_keywords" />
    <meta name="description" content="meta_description" />
    <meta property="og:title" content="title" />
    <meta property="og:description" content="meta_description" />
    <link rel="stylesheet" href="css/style.css" />
    <script type="text/javascript" src="js/lpc.js"></script>
</head>
<body>
    <section data-section="section" style="height:1367px;"><!-- Main section - must have height definition -->
        <div data-section="wrap"><!-- Main wrapper that limits module width -->
            <!-- Here goes modules -->
        </div>
    </section>
</body>
</html>
```

* Sections gives option to divide landing-page structure. 
* 100% width in section allows settings repeated background on whole screen

#### Modules

You can put them in sections. They are the main ingredient of a landing-page

##### Text
    
Basic module for setting texts. Allows formatting, linking and embedding custom fonts.

```html
<div data-editable="text" style="width: 350px; height: 125px; top: 374px; left: 325px;">
    <div style="text-align: center; font-size: 18px; font-family: Helvetica, sans-serif;">
        Lorem Ipsum Dolor Sit Amet
    </div>
</div>
```

##### Box
    
* Allow for creating groups of modules (similar to photoshop). 
* Can take individual property (background or border) independent from elements that are embeded inside it. 
* Allow correct rendering for 1 column landing page on mobile. 

Example below presents box with two independent text module inside:

```html
<div data-editable="box" style="width: 300px; height: 225px; top: 143px; left: 368px;">
    <div data-editable="text" style="width: 350px; height: 125px; top: 374px; left: 325px;">
        <div style="text-align: center; font-size: 18px; font-family: Helvetica, sans-serif;">
            This is first text module
        </div>
    </div>
    <div data-editable="text" style="width: 350px; height: 125px; top: 374px; left: 325px;">
        <div style="text-align: center; font-size: 18px; font-family: Helvetica, sans-serif;">
            This is second text module
        </div>
    </div>
</div>
```

##### Button
    
Allow to present links in form of buttons. Example below presents linked button with defined title.

```html    
<div data-editable="button" style="width: 250px; height: 75px; top: 963px; left: 375px;">
    <a href="http://www.getresponse.com" title="GetResponse"></a>
    <button type="button"><div>Button</div></button>
</div>
```

##### Image
    
Allow to embed images. Images can be loaded from template or from outside source.

```html    
<div data-editable="multimedia:image" style="top: 30px; left: 180px; width: 599px; height: 344px;>
    <img src="1/img/02.png" alt="Lorem Ipums" width="599" height="344">
</div>
```

##### Webform

Allow to subscribe to one of user's campaign
    
* 'action' param must be empty. Target campaign is set outside of the template in landing-page preference panel.
* Labels position can be add by one of class show below to the "wf-item-pos" class:
    * class "type-inline": label on the same line as field
    * class "type-placeholder": label value inside field
* Lack of additional class results in label above field.

Because of this mechanism:

* tags with "wf-item" cannot have 'left' position,
* tags with "wf-item-pos" cannot have 'top' position.

```html
<div data-editable="webform" style="top:147px; left:0;">
    <form action="" accept-charset="utf-8" method="post">
        <div class="wf-wrap" style="width:800px; height:160px;">
            <div class="wf-item" style="top:5px;">
                <div class="wf-item-pos" style="left:195px;">
                    <div class="label">
                        <label style="font-family:'Helvetica Neue', Helvetica, sans-serif; font-size:12px; font-weight:300; line-height:12px; color:#000; padding:0 0 6px 0;">NAME</label>
                    </div>
                    <div style="width:194px; height:43px;">
                        <input type="text" name="name" style="font-family:Helvetica, Arial, sans-serif; font-size:16px; color:#000; padding-left:10px; border:1px solid #000; border-radius:2px;">
                    </div>
                </div>
            </div>
            <div class="wf-item" style="top:5px;">
                <div class="wf-item-pos" style="left:410px;">
                    <div class="label">
                        <label style="font-family:'Helvetica Neue', Helvetica, sans-serif; font-size:12px; font-weight:300; line-height:12px; color:#000; padding:0 0 6px 0;">EMAIL</label>
                    </div>
                    <div style="width:194px; height:43px;">
                        <input type="text" name="email" style="font-family:Helvetica, Arial, sans-serif; font-size:16px; color:#000; padding-left:10px; border:1px solid #000; border-radius:2px;">
                    </div>
                </div>
            </div>

            <div class="wf-item" style="top:109px;">
                <div class="wf-item-pos" style="left:304px;">
                    <div style="width:191px; height:42px;">
                        <button type="submit" value="Sign Up" style="font-size:16px;">Sign up!</button>
                    </div>
                </div>
            </div>
        </div>
    </form>
</div>
```

##### Social
    
Allow to embed social media links.
    
* Facebook
* Twitter
* Pinterest
* Google Plus
* LinkedIn

```html
    <div data-editable="social" data-type="facebook" style="height: 25px; width: 90px;">[[facebook]]</div>
    <div data-editable="social" data-type="tweet" style="height: 25px; width: 90px;">[[tweet]]</div>
    <div data-editable="social" data-type="pinterest" style="height: 25px; width: 90px;">[[pinterest]]</div>
    <div data-editable="social" data-type="googleplus" style="height: 25px; width: 90px;">[[googleplus]]</div>
    <div data-editable="social" data-type="linkedin" style="height: 25px; width: 90px;">[[linkedin]]</div>
```

##### Video
    
Allow to embed video uploaded to YouTube
Player can be customized with additional parameters:
    
* "autohide=0" will show YouTube controls
* "autohide=1" will hide YouTube controls
* "autoplay=1" will autoplay movie after landing-page is loaded
* "loop=1" will loop the movie
* "showinfo=0" will hide movie title

Params are defined in "src" property in iframe tag

```html    
<div data-editable="video" style="width: 320px; height: 240px;">
    <iframe src="https://youtube.com/embed/2qEgVBsjyJU?autoplay=1" frameborder="0" height="100%" width="100%" data-src="//youtube.com/embed/2qEgVBsjyJU"></iframe>
</div>
```

##### Line

Allow display vertical and horizontal lines.
    
* for horizontal lines data-type="hline"
* for vertical lines data-type="vline"
* Types: solid, dotted, dashed 
* thickness of line is defined with "border-top" property when "height": 0

```
<div data-editable="shapes:line" data-type="hline" style="width: 300px; height: auto; top: 429px; left: 345px;">
    <div style="border-top: 5px dotted #ff0000; height: 0px;"></div>
</div>
```
