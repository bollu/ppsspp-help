<link rel="stylesheet" type="text/css" href="style/stylesheet.css" />



PPSSPP Help
===========

About:
------

PPSSPP is a PSP emulation project created by Henrik Rydgard in 2012, and since the start
many more people have contributed improvements.

+ [How to play](#how-to-play)
+ [FAQ](#faq)
+ [Settings](#settings)
+ [Changelog](#changelog)


<a name = 'how-to-play'></a>

How to play games:
------------------
To legally turn your PSP games into .ISO files, you need to install "Custom Firmware" on your PSP. Google for that. Then follow these steps:
* Insert the UMD into your PSP.
* Connect your PSP to your PC with a USB cable.
* At the PSP menu, press Select. In the menu that pops up (only on Custom Firmware), choose to UMD as USB Device.
* Still in the PSP menu, choose USB Connection in the Settings menu (to the left).
* On your PC, a folder will pop up, containing a virtual ISO file. To copy the game to your PC, simply drag this to somewhere on your harddrive and the copy will start. Done!

There are also tools to turn ISO files into CSO (compressed ISO) files to save space.

If you have digital downloads on your PSP, they can be used directly on PPSSPP. Just copy the EBOOT.PBP over. Note that this has not been tested as much as ISO loading so there may still be issues with some games.
<a name = 'faq'></a>

FAQ:
----
__How to get games?__

Again, we don't support piracy. Please read the section "How to play games".

__My save states won't load in 0.9.5!__

Save states are tricky in an emulator that's not fully completed yet, as we haven't found all the state we need to save. Before 0.9.5, we would just copy all the state straight to an unstructured file. As the amount of state differed between the versions, no two were really compatible. From 0.9.5 and forwards, we have created a structured format where we can add new sections as needed.

So currently it's like this:

States from versions before 0.9.5 will never load in a later version
States from 0.9.5 and onwards WILL load in future versions!
That means that your 0.9.1 save states is stuck on 0.9.1, unfortunately.

There is however a workaround that often works:

Load your state in 0.9.1
Save your game using real in-game saves (a save point in an RPG or a save choice in menu or something)
Copy your Memstick/PSP/SAVEDATA directory from 0.9.1 to 0.9.5
Load the real save in 0.9.5
Now you can keep save-stating.
This is unfortunately quite tricky to do on Android (but not too hard on PC).

__What does this option do?__

PPSSPP has lots of options. All of them improve some game for someone, otherwise they would have been deleted by now - I try to keep the number of options sane at least.

__Do I need a BIOS file to run PPSSPP, like with PSX emulators?__

No. PPSSPP simulates the BIOS (not really a BIOS on the PSP, more like an internal OS).

__Where can I get PPSSPP for iOS?__

You need a jailbroken iOS device, running iOS 6 or later. See the Downloads page for more info.

__PPSSPP is awesome! How do I donate to the project?__

Buy PPSSPP Gold! Available for Windows and Android. It's the same as the regular version functionally (see Why Gold?), but by buying it you support the development of PPSSPP.

__What is the JIT?__

To emulate advanced systems like the PSP fast, the emulator needs to translate the machine code language of the PSP to the machine code language of your PC or mobile device at runtime. This is done with a "Just-In-Time recompiler" or JIT, also known as a Dynarec. PPSSPP has JITs for x86 and ARM.

For a JIT to function, an app needs to have the ability to generate machine code at runtime. This is allowed on Windows, Mac, Linux and Android, while it is completely disallowed on non-jailbroken iOS and on App Store Mac apps, and on Windows Phone 8.

__How do I install game DLC?__

Install it exactly the same way as you would on a PSP, that is, copy the files to PSP/GAME or PSP/SAVEDATA (depending on the DLC) on the memory stick. In the Android version of PPSSPP, the memory stick is simply the SD card or USB storage of your phone, create a PSP folder in the root of that. On all other versions, the memory stick is the "memstick" subdirectory in the PPSSPP folder.

__Why is PPSSPP not available for Windows Phone?__

Windows Phone is, like unjailbroken iOS, a very restrictive environment where apps are not allowed to generate code at runtime. This prevents the JIT to work, which means that even if we ported the emulator, it would run very slow.

Also, OpenGL is not available on Windows Phone, making porting a big project which isn't worth it because of the low possible speed we can get.

In addition, I don't have a Windows Phone device.

__Will PPSSPP be able to emulate the PSP Vita in the future?__

PSP Vita is a completely different platform and it's still very secure, meaning that there's no way to decrypt games, making any emulation attempt impossible unless this changes. Also, it's far more powerful so emulating it at full speed on an Android phone is years off anyway.

__Why is PPSSPP so fast?__

You're probably a Windows user. Because x86 CPUs are damn fast, PC GPU drivers are good, we have a fairly advanced x86 JIT, it's written in C++ and I rock.

__Why is PPSSPP so slow?__

You probably run PPSSPP on a mobile device. The ARM JIT is basic and needs improvement, and these devices simply are not very strong yet, no matter what marketing tells you, or their graphics drivers SUCK. An example of the latter would be the Nexus S.

__Why is the emulator called PPSSPP?__

Why not?

__The Windows version doesn't start!__

You may need to install the VC2010 redist (some DLL files). Also, if it still doesn't work, try installing the latest DirectX and OpenGL drivers for your graphics card.

__Can I use my gamepad to control PPSSPP?__

PPSSPP has built-in XInput support on Windows so it will "just work" with any Xbox 360 pad that you plug into your PC. On Android the gamepad situation is not very good yet, the Xperia Play buttons will work but not the touch sticks, for example.

__What are the PC CPU and GPU requirements?__

Any reasonably modern CPU with support for SSE2 will be just fine, and any GPU that can handle OpenGL 2.0 should have no issues. You should make sure to install the latest graphics drivers available though. Windows XP or later is required, Windows 7 or 8 is recommended.

__Where are the "pre-x.y" versions everyone is talking about in the forum?__

<div onclick="location.href='http://buildbot.orphis.net/ppsspp/';" >Here</div>

__What are CSO files?__

CSO are compressed ISO files that can be played directly, decompressing on the fly. Very useful to save space on your Android device, for example. There are a large number of programs around the web that can create CSO files from ISOs, just Google for it.

__I've managed to fix a bug, how do I get the fix into PPSSPP?__

If you know GitHub, you know the drill - just make a pull request with the changes, in a clone of the PPSSPP repository. If you don't know Git(Hub), feel free to ask for help.

__My favorite game doesn't work in PPSSPP. What can I do?__

You can either help out with fixing it, or wait until someone does.

__The Windows version won't run, missing XInput.dll__

Install DirectX.

__Where's the MacOSX build?__

Nobody has volunteered to prepare and package one yet. Contact me if you're interested.

<a name = 'settings'></a>

Game Settings:
--------------

<!-- graphics -->

### Graphics ####

#### Rendering Mode ####

__Buffered mode__

This is the standard mode. The PSP can render to any location in its VRAM and use as either the scanout buffer (what you see on the screen) or textures. Many games use this to implement special effects, or simply to implement 30fps (you need to show the same buffer twice). We simulate this by allocating an OpenGL FBO for every PSP framebuffer location.

Note: This option is mandatory for many games, including __Grand Theft Auto Liberty City Stories__ and __Grand Theft Auto Vice City Stories__, which show black screen without it.

__Non-buffered mode__

Disabling the buffered mode is a speed hack that may or may not speed up some games, and may cause graphical glitches and/or screen flickering. Another effect of disabling this option is that you lose the ability to change render resolution independently of window size.

Due to emulation bugs, some games are improved in non-buffered mode.
* __Sword Art Online__ It fixes the overbrightness issue.
* __Wipeout Pulse and Pure__ It fixes the overbrightness issue.

__Read framebuffers to memory (CPU)__

This mode fixes graphical issues in some games, but it's very expensive as it copies the whole content into buffer and then covert them into pixels through CPU. Games that do not need it may be worse with this option. Following are the games that apparently works with this mode:

* __Breath of Fire 3__
* __Danganronpa__
* __Final Fantasy Tactics: The War of the Lions__ It fixes the transparency in menus open in the map.
* __Soul Calibur: Broken Destiny__ It allows to take photos of created characters.
* __The Legend of Heroes: Trails in the Sky__ It fixes the transparent menus and the screenshots to create icons of saved games.
* __The Third Birthday__
* __Ys Seven__ It fixes the minimap, the transparency in the full map, the screenshots to create icons of saved games and the darkness in Flame Sanctum.

__Read framebuffers to memory (GPU)__

This is the same as the option above, but this is faster as it uses GPU to convert those pixels asynchronously. However, it only works on PC and optimized for Nvidia cards.


#### Framerate control ####

__Auto FrameSkip__

Allows the frames to skip automatically when the game can't reach 100% VPS. Note: You need to specify the max number of frames to skip in Frameskipping before using it.

__Frameskipping__

Especially on mobile platforms, the graphics rendering is the performance bottleneck. Hence, speed
can be improved by simply skipping the rendering process on every other frame, or more. The drawback
is of course that the framerate will decrease, and if you combine it with multithreading, there may
be flickering issues. The setting to control this is called Frameskipping.

__Force 60 FPS or less__

Some games (such as both __God of War__ games) have a bug related to rendering. This hack helps to keep these games in check and makes them playable.

__Alternative speed__

This option allows to play the game at a constant specific speed that you can choose. 100% is the normal speed.
You can choose 200% to make the game running twice faster instead of unlimited speed if the computer (or device) is powerful enough.
Speeds below 100% allow to play in slow motion.


#### Features ####

__Postprocessing Shader__ Note: *buffered rendering __must__ be enabled to use this*

Allows one to use custom shaders that add effects such as bloom and grayscale.


Types of shaders:

*`Off`*: Disable shaders altogether.

*`FXAA Antialiasing`*: Reduces jagged edges on 3D objects using Fast Approximate Anti-Aliasing (FXAA) algorithm.

*`CRT Scanlines`*: Simulates CRT screen like effect by drawing horizontal lines that updates per second.

*`Natural Colours`*: Slightly enhances contrast and colours.

*`Grayscale`*: Renders in grayscale (black and white).

*`Vignette`*: Renders with a sepia tone (old-school photograph look).

*`Bloom`*: Enhances brightness and gives glow like effect.

*`Sharpen`*: Sharpens the whole screen.

*`Inverse Colors`*: Inverts the colors.

*`Scanlines`*: Creates a CRT screen like effect by drawing horizontal lines and simulating screen tint.

*`Color`*: Creates a cartoon-like effect.

*`4xHqGLSL`*: Enhances sprites by smoothing pixels and scaling textures.

*`AA-Color`*: Reduces jagged edges on screen with additional contrast and colours.

*`Spline36 Upscalar`*: Scales the sprites using Spline algorithm. Note: It requires integer support in shaders which currently isn't supported by android GPUs.

<!-- end shaders -->


__Fullscreen(PC Only)__

Causes PPSSPP to stretch its size to that of the display while mantaining the aspect ratio of real PSP.

__Stretch to display__

Causes PPSSPP to stretch it's size to that of the display. This destroys the aspect ratio.

__Mipmapping__

Enabling mipmapping will grant a performance increase, but will cause PPSSPP to look slightly blurry as a result, as mipmapping pre-calculates the filtered textures and store them to use in games.


#### Performance ####

__Rendering Resolution__

Allows to choose the resolution to render 3D graphics. The PSP resolution is 480 x 272 and this option scales the resolution N times in each dimension, for instance, 2X scales the resolution to 960 x 544.
Consequently, it improves the graphics in larger screen, because the real PSP is small. The higher the resolution, less pixelated the 3D models will look.
Setting it to *Auto* will make PPSSPP use the resolution that is near the window size or the resolution of your screen when playing in fullscreen.

__Vsync__ 

The display of your device refreshes many times per second (usually 60 times per second). If this option is enabled, then PPSSPP will only draw during every refresh. This will cause it to look much smoother. However, this is bit expensive as it forces the device to run at same refresh rate. If you are getting low performance with it then disable it.

__Hardware Transform__

Vertex Shader uses it to make all the complex calculations that are required for rendering in the hardware (GPU or Video Card) instead of doing it on the processor. It tends to be much faster and gives a performance boost when enabled.
However, due to bugs, some games are fixed when this option is disabled:
* __Dangan Ronpa__ It fixes the crashes.
* __Tekken 5 Dark Resurrection__ It fixes the health bars.

__Software Skinning__

It gives a performance boost in some games that extensively uses skeletal animation on characters. It uses CPU to compute them which decreases their rendering time thus increasing performance. However, some games like *Monster Hunter* games slows down with it.

__Vertex Cache__

This gives a performance boost when enabled as it skips few calculations on geometry, disable it if you see strange graphical glitches. Performance improvement will depend on game and GPU.

__Lazy texture caching__

Causes glitches in some games like Danganronpa and Growlanser but increases performance. [TODO: Explain]

__Retain changed textures__

Speeds up Popolocrois [TODO: Explain]


__Low quality Spine / Bezier Curves__

Computers use equations known as Bezier Curves to draw curves. However, this equation is computationally intensive. Hence, a low quality version of this equation will give better performance, but looks poorer. Enabling this option will provide a performance boost at the cost of graphical fidelity.
 

#### Texture Scaling ####
Texture scaling improves texture detail. However, it is a very expensive process and can cause slowdown.

PSP games generally have quite low texture detail, as more isn't needed due to the low resolution of
the PSP display, and the lack of RAM and VRAM available. The Texture Scaling feature uses a high quality
scaling filter to give the illusion of sharper texture detail. Doesn't work great with all art styles,
but some games are very much improved.

There is generally no point in going beyond 3x texture scaling unless you are running at very high resolutions.

__Upscale Level__

The type of Upscale to use.

*`Auto`*: Scales textures dependently of rendering resolution.

*`Off`*: Disable Texture Upscale.

*`2x`*: Scales textures upto 2x of original texture size.

*`3x`*: Scales textures upto 3x of original texture size.

__Upscale Type__

There are various algorithms that are used to upscale. Here, a particular algorithm can be selected.

Types of Upscale algorithms:

*`xBRZ`*:  Scales the texture based on pattern recognition similar to HQx.

*`Hybrid`*: Scales the textures bilinearly.

*`Bicubic`*:  Scales the textures using spline equations.

*`Hybrid + Bicubic`*:  Combines the effect of Hybrid and Bicubic.

__Deposterize__

Smoothes posterized gradients from low-color-depth (e.g. 444, 565, compressed) textures when texture scaling is enabled.

#### Texture Filtering ####

PSP games were made to run at 480x272, and rendering them at other resolutions sometimes causes problems
like little lines at the boundaries of textures. This can sometimes be worked around by tweaking filtering settings.

__Anisotropic Filtering__:

Enhances the image quality, clarity and crispness of textured objects. This is generally free on GPU and doesn't decrease performance.

__Texture Filter__

*`Auto`*: Treat filtering on objects just like original PSP.

*`Nearest`*: Forces Nearest Filtering on the whole screen. It sharpens the 2D sprites and text, but the 3D graphics looks worse with it.

*`Linear`*: Forces Bilinear Filtering on the whole screen. Basically smoothes the HUD and 2D graphics, but can cause artifacts.

*`Linear on FMV`*: Forces Bilinear Filtering on videos only.


#### Hack Settings ####

These options are workarounds for things we don't emulate properly in some specific games, or speed improvements that may cause problems. Be careful, most of these options break games.

__Timer Hack__

It trades speed for accuracy by not stepping the emulated PSP CPU in correct timing. Enabling it can give performance increase in some games. Try experimenting with it.

__Disable Alpha Test__

Disabling Alpha Test greatly improves performance on PowerVR GPUs (common on mobile) as that feature is extremely slow on them. While it gives slight performance improvement on other devices.

__Disable Stencil Test__

Enabling this will disable stencil test on objects. [TODO: explain which game requires it to work properly]

__Always Depth Write__

Enabling this simply assumes that all objects will depth write, causing severe graphical glitches on many games. Few games require this option enabled to work properly.

* __Saint Seiya Omega__ It fixes invisible characters.

__Texture Coord Speedhack__

Enabling this greatly improves performance as it pre-scales the texture coordinates instead of doing it in real time, but can cause severe graphical glitches. Please do not report bugs on forums with this option enabled.


#### Overlay Information ####

__Show FPS Counter__

Shows performance counters at the top right corner. 

Types of Counters:

*`FPS`*: Shows the number of frames per second being rendered.

*`Speed`*: Shows the speed which the game is running at. 100% is the normal speed.

*`Both`*: Shows both the FPS and the Speed.

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
Controls background volume.

__Enable Sound__
Enable and disable all sounds.

__Low latency audio__
An experimental feature that might help reduce audio lag. It also generally causes stuttering and other audio distortion.

<!-- Controls -->

### Controls ###

__Control Mapping__
Rebind PSP controls to keyboard, game pad and virtual buttons.

__Haptic Feedback__
If this is enabled, the device will vibrate every time a button is pressed.
Useful in mobile devices for tactile feedback.


#### On-screen touch controls: ####

This option can be enabled to use on-screen controls. This is useful on
devices such as phones and tablets with no hardware buttons.

__Button Opacity__

It is used to change the opacity of buttons. An opacity of 0 is completely transparent.
Opacity of 100 is fully opaque

__Buttons scaling__

It is used to change the size of buttons. Higher the value of button scaling, larger
the buttons will be.

#### Custom Layout: ####

It is used to move on-screen buttons to custom positions.

Hold down a button and drag the button to the desired location. Then click on
Back to save changes.

To Reset changes, press the __Reset__ button.

#### Button Visibility ####

To modify button visibility, click on __Custom layout__ in the __Controls__ menu.
Then, click on the __Visibility__ button in the left. Here, buttons can be
made visible or invisible by toggling the buttons.
<!-- TODO: make this explanation better -->
<!-- system -->

#### On-screen touch controls: ####

__Ignore Windows Key__

It disables the Windows key ingame (so you don't pop up the Start menu by accident).

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

It is used to enable or disable cheats in PPSSPP.

[This is something I know nothing about. Someone who actually knows about this (maybe UnknownBrackets) will have to edit this section]

#### General ####

<!-- begin Developer options-->

##### Developer Tools: #####

This section of PPSSPP contains tools that are useful for PPSSPP developers. Be careful when changing options in this section.

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

*****

#### General ####

__Check for new versions of PPSSPP__

Enabling this option will automatically check for new version of PPSSPP, and inform the user when one is available.

__Clear Recent games list__

This will clear the recent games screen.

__Restore Default Settings__

This restores the default settings provided by PPSSPP.

__Auto Load Newest Savestate__

Enabling this will automically load the last saved savestate.

__Enable compatibility server reports__

Enabling this will send the log reports to the PPSSPP server.

#### Networking ####

__Enable networking/wlan(beta)__

Enabling this will enable wlan (that's what it says, anyway) [TODO: Explain better..]

#### PSP Settings ####

__PSP Model__

Changes emulated PSP model. [TODO: Explain the difference..]

__Change nickname__

It changes the nickname which is used by games.

__Screenshots as PNG__

It allows you to take screenshots in .png format.

__Daylight Savings__
It is used to enable and disable daylight savings in PPSSPP's time calculation.

__Date Format__

It is used to change the date format. Supported formats are:


__`YYYYMMDD`__ - eg: 2013 12 01 (1st December 2013)

__`MMDDYYYY`__ - eg: 12 01 2013 (1st December 2013)

__`DDMMYYYY`__ - eg: 01 12 2013 (1st December 2013)

[TODO: Idk where this is used. Should write about what this is for]

__Time format__

It is used to change the time format. Supported formats are __`12 hours`__ and __`24 hours`__

__Conformation Button__

By default, the PSP uses the __`X`__ action button to confirm actions. This can be changed to __`O`__.



<a name = 'changelog'></a>


Changelog:
----------

##Version: 0.9.7##

* Several scheduling and audio fixes, fixing black screens in Yu Gi Oh games among other things.
* Screen rotation support on Android
* Initial multitouch support on Windows 8 for on-screen controls.
* Large improvements to the software renderer (still not really playable, but looks right more often than not)
* Bugfixes and new VPL allocator, fixing Pangya Golf performance problems.
* Some mpeg/video playback fixes, fixing Parappa The Rapper and others.
* Fix save state bugs causing incompatibility between 32 and 64-bit platforms.
* Symbol map/debugger improvements
Depth buffer copy, fixing Jeanne D'arc. May cause minor slowdowns though, this will be worked around in the future.
* MsgDialog fixes


##Version: 0.9.6##

* Large general speed improvements and assorted bug fixes
* "Software Skinning" option which speeds up many games with animated 3D characters (but may slow down a few, like Monster Hunter games - experiment with turning it off)
* Various fixes around stencil/alpha, reducing glow problems in Wipeout and Gods Eater Burst.
* Timing improvements making more games run at the correct FPS, also fixing some audio issues
* More debugger features
* Option for four-way touch dpad, avoiding diagonal dpad issues
* Better looking and individually resizable touch controls
* Add ability to switch UMD in multi-disc games (works for most)
* Emulate PSP-2000 rather than the 1000 model by default. Not much different in practice.
* Automatic install of games from ZIP files, like demos and many homebrew.
* VERY basic ad-hoc online play support, to be improved in future versions. See below.
* Software renderer improvements


##Version: 0.9.5##

* Many, many emulation fixes:
  - bezier/spline curve support, fixing LocoRoco and others
  - stencil clear emulation, fixing Final Fantasy IV text
* Performance improvements in some games
* Post-processing shaders like FXAA, scanlines, vignette
* More solid save states (we will try to keep them working from now on. Save states only upgrade forward,
  not backward to older versions though).
* Change render resolution independently of window size
* Massive debugger improvements
* Win32 menu bar is now translatable
* Multiple UI bugs were fixed, and the UI instantly changes when a new language is selected
* Win32: Ability to store PPSSPP's config files and memory stick files in places other than the same directory
* Android-x86 support
* Unofficial port for modified Xbox 360 consoles
* Atrac3+ plugin no longer required. Symbian now supports Atrac3+ audio.
* Symbian audio and ffmpeg is now threaded for more consistent media processing.
* Haptic feedback support for mobile devices.
* Accurate system information for mobile devices.
* Qt audio has been fixed.
* Analog controller support for Blackberry.


##Version: 0.9.1##

* Bugfix release


##Version: 0.9.0##

* Much improved control mapping, and autoconfig for a few devices like Shield
* Large speed boosts in many games
* Huge improvements to our internal PSP debugger by Kingcom!
* A number of new games became compatible, such as Final Fantasy Tactics which just has some audio issues left.
* A completely redesigned user interface, unlike the previous static one this one can grow with the emulator and has keyboard/controller navigation support, for the full lean-back experience!
* Improved frameskipping, increasing playability on slower devices.


##Version: 0.8.1##

* A crash fix release, fixing a couple of possible crashes around downloading the Atrac3+ plugin.


##Version: 0.8.0##

* Full video and audio playback in most games (audio requires an optional plugin)
* Huge increases in compatibility! Final Fantasy: Crisis Core is fully playable on fast devices, for example.
* Lots of little things like easy screenshot taking, the beginnings of a cheat feature, etc


##Version 0.7.6:##

* Serious bugfix which improved games compatibility across the board. 
* Multi lingual support for PPSSPP UI. 

##Version 0.7.5:##

* Many more games run and some games run faster
  - The God of War games should now run well on modest PCs and for example the Monster Hunter games are becoming playable on fast phones (although without sound).

* Improved UI
+ Recent list and game icons in the game selector


##Version 0.7.0:##

* Compatibility has gone up dramatically
* Speed has increased drastically (especially on mobile)
* Horizontal tilt control
* Some newly playable games are:
  - God of War (very slow though, but this will probably be fixed in the near future)
  - Virtua Tennis
  - Megaman: Maverick Hunter X
  - Saint Seiya
  - Ace Combat X goes in-game


##Version 0.6.0:##

* Has a preliminary ARM JIT (greatly boosts speed on Android and other ARM platforms)
* Vertex caching (improves performance quite a bit)

##Version 0.5.0:##

* Large compatibility improvements
* Much better audio
* Many graphics fixes
* Savegames and savestates working in many games


##Version 0.4.0:##

* Graphics improvements
* Compatibility improvements


##Version 0.3.1:##

* Many fixes
* More games playable


##Version 0.1:##

* First release
