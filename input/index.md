<link rel="stylesheet" type="text/css" href="style/stylesheet.css" />

PPSSPP Help
===========

About:
------

PPSSPP Is a PSP emulation project that was started by Henrik Rydgard.

+ [How to play](#how-to-play)
+ [FAQ](#faq)
+ [Settings](#settings)
+ [Changelog](#changelog)


<a name = 'how-to-play'/>

How to play games: 
------------------
To be Constructed

<a name = 'faq'/>

FAQ: 
----
To be Constructed

<a name = 'settings'/>

Game Settings:
--------------

<!-- graphics -->

### Graphics ####

#### Rendering Mode ####

__Mode__

the PSP can render to any location in its VRAM and use as either the scanout buffer (what you see on the screen) or textures. Many games use this to implement special effects, or simply to implement 30fps (you need to show the same buffer twice). We simulate this by allocating an OpenGL FBO for every PSP framebuffer location.
Disabling it is a speed hack, that may or may not speed up some games, and may cause graphical artefacts and/or screen flickering. Another effect of disabling this option is that you lose the ability to do 2x supersampling.

#### Framerate control ####

__Frameskipping__

this option allows frames to be "skipped" if it is taking too much time to draw them. However, this
will create __screen flickering__. This option can be used to increase performance. 

__Force 60 FPS or less__

Some games (such as god of war) have a bug related to rendering. This hack helps keep these games in check and makes them playable.

__Alternative speed__
[don't know what this does off the top of my head. will have to look and see]

#### Features ####

__Postprocessing Shader__ Note: *buffered rendering __must__ be enabled to use this*

Allows one to use custom shaders that add effects such as bloom and grayscale.


Types of shaders:

*`Off`:*: Disable shaders altogether

*`FXAA Antialiasing:`*

*`Natural Colours`:*

*`Grayscale`:* Renders in grayscale (black and white)

*`Vignette`:* Renders with a sepia tone (old-school photograph look)

*`Inverse Colors`:* Inverts Colors

*`Scanlines`:* Creates a CRT screen like effect by drawing horizontal lines

*`4xHqGLSL`:* [idk]

*`AA-Color`:* [idk]

<!-- end shaders -->


__Stretch to display__

Causes PPSSPP to stretch it's size to that of the display. This destroys the aspect ratio.

__Mipmapping__

Disabling mipmapping will grant a performance increase, but will cause PPSSPP to look slightly blurry as a result. [TODO - explain mipmapping]


#### Performance ####

__Rendering Resolution__
[TODO]

__Vsync__ 

The display of your device refreshes many times per second (usually 60 times per second). If this option is enabled, then PPSSPP will only draw during every refresh. This will cause it to look much smoother. However, this requires great performance [TODO - explain how FPS drops by half if a frame is missed]. Disabling this option provides a performance boost.

__Hardware Transform__

Vertex Shader uses to make all the complex calculations that are required for rendering in the hardware (GPU or Video Card) instead of doing it on the processor. It tends to be much faster and gives a performance boost when enabled.

__Vertex Cache__

This gives a performance boost when enabled
[TODO - explain caching theory >_>" . This maybe futile...]


__Low quality Spine / Bezier Curves__

Computers use equations knows as Bezier Curves to draw curves. However, this equation is computationally intensive. Hence, a low quality version of this equation will give better performance, but looks poorer. Enabling this option will provide a performance boost at the cost of graphical fidelity.
 

#### Texture Scaling ####
Texture scaling improves texture detail. However, it is a very expensive process and can cause slowdown.

__Upscale Level__

The type of Upscale to use.

*`Off`:*: Disable Texture Upscale

*`2x`*: [TODO - explain]

*`3x`*: [TODO - explain]

__Upscale Type__

There are various algorithms that are used to upscale. Here, a particular algorithm can be selected.

Types of Upscale algorithms:

*`Hybrid`*:  [TODO - explain]

*`Bicubic`*:  [TODO - explain]

*`Hybrid + Bicubic`*:  [TODO - explain]

#### Texture Filtering ####

__Anisotropic Filtering__: [TODO]

__Texture Filter__: [TODO]


#### Hack Settings #### *most of these option break games. be careful*

__Disable Alpha Test__
This has been shown to create a performance gain in devices which use PowerVR chipsets.
[TODO - explain what this does]

__Disable Stencil Test__
[TODO - explain what this does]

__Always Depth write__
[TODO - explain what this does]

__Texture Coord Speedhack__
[TODO - explain what this does]

#### Overlay Information ####

__Show FPS Counter__

Shows performance counters at the top right corner. 

Types of Counters:

*`FPS`*: Shows the number of frames per second being rendered

*`Speed`*: Shows the [i'm not sure, virtual processor speed?]

*`Both`*: Shows both the FPS and the Speed

__Show debug statistics__

Shows realtime information which is very useful for debugging games. It is primarily a developer option and is useless to others.

#### Debugging ####

__Dump next frame to log__ *this option can only be accesses in-game*

Dumps the entire log generated by PPSSPP during the next frame into a log file. This is useful to send bug reports to developers.

__Software Rendering__ *this option is experimental*

On computers which do not have a dedicated GPU (Video card), a *Software renderer* can be used. However, this will be orders of magnitude slower, and is generally unplayable. 


<!-- Audio -->

### Audio ###

__SFX volume__
Controls volume of special effects. 

__BGM volume__
Controls background volume

__Enable Sound__
Enable and disable all sounds

__Low latency audio__
An experimental feature that might help reduce audio lag. It also generally
causes stuttering and other audio distortion  

<!-- Controls -->

### Controls ###

__Control Mapping__
Rebind PSP controls to keyboard, game pad and virtual buttons.

__Haptic Feedback__
If this is enabled, the device will vibrate every time a button is pressed.
Useful of mobile devices for tactile feedback


#### On-screen touch controls: ####

This option can be enabled to use on-screen controls. This is useful on
devices such as phones and tablets with no hardware buttons.

__Button Opacity__

Used to change the opacity of buttons. An opacity of 0 is completely transparent.
Opacity of 100 is fully opaque

__Buttons scaling__

Used to change the size of buttons. Higher the value of button scaling, larger
the buttons will be.

#### Custom Layout: ####

Used to move on-screen buttons to custom positions.

Hold down a button and drag the button to the desired location. Then click on
Back to save changes.

To Reset changes, press the __Reset__ button.

#### Button Visibility ####

To modify button visibility, click on __Custom layout__ in the __Controls__ menu.
Then, click on the __Visibility__ button in the left. Here, buttons can be
made visible or invisible by toggling the buttons.
<!-- TODO: make this explanation better -->
<!-- system -->

### System ###

#### UI Language ####

__Language__
Change the default language of PPSSPP. 

#### Emulation ####

__Fast Memory (Unstable, use with caution)__ *option only applied after a reset*

 This option changes PPSSPP such that that all memory accesses the game makes is considered valid. This, there is an increase in speed. However, this can also *result in crashes* if a game does an invalid memory access. 

__Multithreaded (Unstable, use with caution)__

This option allows PPSSPP to do multiple tasks at the same time. This creates a performance gain. However, this can also cause [not sure how to describe race conditions], leading to crashes
<!-- TODO: come up with a proper explanation of threads-->

__I/O on thread (Unstable, use with caution)__

[again, not sure how to explain this]

__Change CPU Clock__

This option controls the Virtual CPU clock. When it is enabled initially, the Virtual CPU will run at 222Mhz (the standard speed of PSP CPU). This speed can be increased or decreased. 

Decreasing the clock, you will get more percents (%) on speed, but less FPS. 

Increasing the clock will cause more FPS and less percent (%). 

This happens because when the virtual clock is high, it increase the strain on your system, and thus PPSSPP becomes slower and the total game speed will drop.
<!-- copy-pasted explanation. need a better one. Linky - http://forums.ppsspp.org/showthread.php?tid=5352 -->


__Atomic Audio Locks__

[Sigh, I'm not sure how to explain this either. Something on the lines of skipping audio if PPSSPP is slowing down (which is not really true but a gross approximation) maybe?]

#### Cheats ####

__Enable Cheats__

Used to enable or disable cheats in PPSSPP.

[This is something I know nothing about. Someone who actually knows about this (maybe UnknownBrackets) will have to edit this section]

#### General ####

<!-- begin Developer options-->

##### Developer Tools: #####

This section of PPSSPP contains tools that are useful for PPSSPP developers. Be careful when
changing options in this section.

###### General:

__Dynarec (JIT)__

To emulate advanced systems like the PSP fast, the emulator needs to translate the machine code language of the PSP to the machine code language of your PC or mobile device at runtime. This is done with a "Just-In-Time recompiler" or JIT, also known as a Dynarec. PPSSPP has JITs for x86 and ARM.

For a JIT to function, an app needs to have the ability to generate machine code at runtime. This is allowed on Windows, Mac, Linux and Android, while it is completely disallowed on non-jailbroken iOS and on App Store Mac apps, and on Windows Phone 8.

<!-- copy pasted from PPSSP's website http://www.ppsspp.org/faq.html -->

__System Information__

Shows device-related information such as the system specifications, OpenGL extensions and OpeGL ES extensions.

__Show Developer Menu__

Can be toggled to display the [Developer Menu](#devmenu) <!-- actually make a subsection about the
developer menu --> while playing a game.

__Enable Debug Logging__

PPSSPP constantly gathers information about its own state while playing a game. This is done to help developers track down bugs and improve PPSSPP. This option can be used to turn this on or off.

__Logging Channels__

PPSSPP logs information into separate channels based on where the log is originating from. Log channels can be enabled and disabled from this menu. This is useful if one wants to track one particular module of PPSSPP.

###### Language:

__Load Language ini__
[TODO]

__Save Language ini__
[TODO]

<!-- end Developer options-->

#### PSP Settings ####

__Daylight Savings__
Used to enable and disable daylight savings in PPSSPP's time calculation.

__Date Format__

Used to change the date format. Supported formats are:


__`YYYYMMDD`__ - eg: 2013 12 01 (1st December 2013)

__`MMDDYYYY`__ - eg: 12 01 2013 (1st December 2013)

__`DDMMYYYY`__ - eg: 01 12 2013 (1st December 2013)

[Idk where this is used. Should write about what this is for]

__Time format__

Used to change the time format. Supported formats are __`12 hours`__ and __`24 hours`__

__Conformation Button__

By default, the PSP uses the __`X`__ action button to confirm actions. This can be changed to __`O`__.


<a name = 'changelog'/>

Changelog:
----------

Version: 0.9.5
