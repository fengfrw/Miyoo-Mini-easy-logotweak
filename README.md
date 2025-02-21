# Miyoo Mini - Easy Logotweak  By Schmurtz
 An app for easy boot logo flashing on the Miyoo Mini and Miyoo Mini Plus

```
!! **                                    Use it at your own risk :                                     ** !!
!! ** logotweak write in the nand of the Miyoo Mini. A bad flash will cause your miyoo Mini to brick.  ** !!
!! **      Check your battery level (don't use it with low battery level) and use a good SD card.      ** !!
```
Easy Logotweak uses the flash binaries "Boot logo changer" created by Eggs.

Easy Logotweak is a based on Advance Menu coupled with a linux shell script which allows to choose a logo and to flash it in an easy way.
It is presented as an app in Miyoo Mini menu.

The community has made some excellent tutorial videos, I invite you to have a look at them, they are presented below.


------------------------------------------------
**Contents:**
* [Download](#download)
* [Installation](#installation)
	* [Onion-OS](#to-use-with-onion-os)
	* [MiniUI](#to-use-with-miniui)
* [Add your own logo in the collection](#add-your-own-logo-in-the-collection)
* [Videos tutorials](#videos-tutorials)
* [Community logos's included](#community-logoss-included-)
* [Release Notes](#release-notes)
* [Detailed documentation](#detailed-documentation)
* [Thanks](#thanks)

------------------------------------------------
## Download

[Click here to get the last version released](https://github.com/schmurtzm/Miyoo-Mini-easy-logotweak/releases)

------------------------------------------------
## Installation

 #### To use with Onion-OS
```
	1 - Open the downloaded archive and extract the content of the archive at the root of your SD card.
	2 - Run the app logotweak, and choose your logo. That' all : power off -> power on to see the result ;)
```
 #### To use with MiniUI
```
	1 - Open the downloaded archive and extract "logotweak" folder in "Tools" folder of your SD card
	2 - Rename the folder "logotweak" to "logotweak.pak"
	3 - Run the app logotweak, and choose your logo, that' all : power off -> power on to see the result ;)
```

## Add your own logo in the collection
```
	- create a new folder in app\logotweak\logos
	- Place your 180 degree rotated image files in this new folder (image1.jpg is required, max file size is about 115kB. image2.jpg and image3.jpg are optional (used for firmware updates)) 
	- Then you can run logotweak to see the result ;)
	
More technical details about logo creation in the detailed documentation below. 
```
------------------------------------------------
## Videos tutorials


An excellent tutorial video about Easy LogoTweak  made by Retro Game Corps (click on the picture to view it) :

(great instructions about how to download from github (deprecated since 3.0.4), the problem on MiniUI mentioned in this video has been solved in version 1.3)

[![An excellent tutorial video made by Retro Game Corps](https://img.youtube.com/vi/fMhtj9VQRSk/0.jpg)](https://youtu.be/fMhtj9VQRSk])


------------------------------------------------

 ## Community logos's included :

<img src="https://raw.githubusercontent.com/schmurtzm/Miyoo-Mini-easy-logotweak/main/tools/Global Preview Generator/Preview.webp" width="300">



 ## Release Notes
```
/*  Release Notes (yyyy/mm/dd):                                                             */
/*  v1.0 - 2022/06/10 :                                                                     */
/*    - Initial release                                                                     */
/*  v1.1 - 2022/06/10 :                                                                     */
/*    - Logos are now dynamically generated with logomake                                   */
/*      (so it's easier to add your own logos, no problem with different firmware version)  */
/*    - New logos included, preview it here                                                 */
/*  v1.2 - 2022/06/11 :                                                                     */
/*    - Logos preview doesn't require to generate a png anymore                             */
/*      (image1.jpg is used to display the preview directly, Thanks to eggs).               */
/*    - image2.jpg and image3.jpg (logos for FW update) are now optional,                   */
/*      by default the one from "Original" folder are used.                                 */
/*    - and two new logos from the community !                                              */
/*  v1.3 - 2022/06/24 :                                                                     */
/*    - Solve display preview problems on MiniUI                                            */
/*  v2.0 - 2022/07/07 :                                                                     */
/*    - Can now navigate between logos with left/right keys                                 */
/*    - Press select to see logo in fullscreen without instructions                         */
/*    - Press menu to exit application                                                      */
/*    - Resolve a problem when displaying instructions on Onion-OS                          */
/*    - Indicates total of logos and current logo number                                    */
/*    - Add a confirmation before flashing                                                  */
/*    - Doesn't backup anymore the current logo (useless most of the time)                  */
/*    - and new logos from the community !                                                  */
/*  v2.1 - 2023/01/02 :                                                                     */
/*    - Firmware version check                                                              */
/*  v2.2 - 2023/01/16 :                                                                     */
/*    - Additional logic for BoyaMicro chips (credits Xpndable)                             */
/*  v2.3 - 2023/03/17 :                                                                     */
/*    - Miyoo Mini+ support                                                                 */
/*  v2.4 - 2023/04/13 :                                                                     */
/*    - Check that used images are really a jpg files                                       */
/*    - Fix Miyoo Mini+ screen offset on firmware 202303262339                              */
/*  v2.5 - 2023/04/17 :                                                                     */
/*    - Better jpg error messages when an image is not valid                                */
/*    - Default flash logos (image2.jpg and image3.jpg) are now more compressed             */
/*    - Fixes for complex paths                                                             */
/*  v3.0 - 2023/04/18 :                                                                     */
/*    - New browsing menu based on AdvanceMenu                                              */
/*    - Thumbnails auto-generation thanks to ImageMagick                                    */
/*    - 94 new boot logos !                                                                 */
/*    - Music : The World Of Douve by DOUVE                                                 */
/*  v3.0.1 - 2023/04/19 :                                                                   */
/*    - Automatically suppress mac metadata files                                           */
/*    - Display the logo in fullscreen before flashing                                      */
/*    - Go back to Advance Menu when cancelling the flash                                   */
/*    - New logos added & removing duplicates                                               */
/*  v3.0.2 - 2023/04/20 :                                                                   */
/*    - Now compatible with DotUI                                                           */
/*  v3.0.3 - 2023/04/30 :                                                                   */
/*    - support for Mini+ firmware 0328 and 0329                                            */
/*    - Custom error message when jpg resolution is bad                                     */
/*    - add and fix some logos                                                              */
/*  v3.0.4 - 2023/08/15 :                                                                   */
/*    - support for Mini firmware 20230611                                                  */
/*    - support for Mini+ firmware 20230628                                                 */
```

 ## Detailed documentation
------------------------------------------------
#### MiyooMini logo tweaking tools (original documentation - manual steps)
<details>
  <summary>Click here to expand </summary>

```
** Mishandling will cause your miyoomini to brick. Use with extreme caution and at your own risk **

logoread	Extract logo images from current NAND
		image1.jpg ....	boot logo
		image2.jpg ....	upgrade screen
		image3.jpg .... super upgrade screen
		- All images are rotated 180 degrees

logomake	Make logo.img from image1,2,3.jpg
		- logo.img size is fixed to 128KB, so the total size of 3 jpg files 
		should be less than 128KB (129,732 bytes max actually)

logowrite	Flush logo.img to NAND
		* miyoomini will brick if image is corrupted. Be very careful *

To change the image, first extract the current images with logoread, modify the image, create logo.img with logomake, 
and then flush with logowrite.

( if the firmware is old (202111201656 or 202112110956), there is no super upgrade screen. in this case, 
logoread will fail to extract the 3rd image, so prepare a dummy image3.jpg after logoread )
```
</details>


------------------------------------------------

#### Reddit Full Tutorial by GumbyXGames
This section describe all the steps necessary before the creation of Easy Logotweak.

It can be usefull to understand all the steps of a custom boot logo flash.
<details>
  <summary>Click here to expand </summary>

```
https://www.reddit.com/r/MiyooMini/comments/v6e1f1/custom_boot_screen_tutorial/

1.Download the Boot Image Changer (https://github.com/jimgraygit/Onion/wiki/6.-Miyoo-mini-apps#boot-logo-changer-credit-eggs)

2.Extract the ZIP

3.Go into the resulting logotweak folder and move the following files out of the folder: image1.jpg, image2.jpg, and image3.jpg

4.Copy the logotweak folder to your microSD card

5.Put your microSD card back into your Mini and power it on

6.Open File Explorer under App from the main menu

7.Browse to the logotweak folder

8.Select logoread by highlighting it and pressing A

9.Select Execute. The screen will go black but then load the App Menu

10.Power the Mini off and remove the microSD card

11.In the logotweak folder on the microSD card there will now be three files: image1.jpg, image2.jpg, and image3.jpg

12.OPTIONAL: I suggest making a backup of the three files in case you want to go back to stock

13.Delete the image you are going to replace:
* image1.jpg is the image shown at boot
* image2.jpg is the image shown when performing a normal firmware update/upgrade
* image3.jpg is the image shown when performing a "Super Upgrade"

14.Copy the new images to the logotweak folder and rename them using the naming in step 13. Be sure the files match the dimensions and file size listed in logotweak_readme.txt

15.Put the microSD card back into your Mini and power it on.

16.Connect your Mini to a USB charger (5v, 1amp) using a USB-A-to-USB-C cable. Do not continue unless you have the Mini connected to external power or you risk bricking it.

17.Open File Explorer under App from the main menu

18.Browse to the logotweak folder

19.Select logomake by highlighting it and pressing A

20.Select Execute. The screen will go black but then load the App Menu

21.Open File Explorer again

22.Browse to the logotweak folder again

23.There should now be a logo.img file in the folder

24.As long as the logo.img folder is present, select logowrite and press A

25.Select Execute. The screen will go black but then load the App Menu

26.You have now flashed the new boot, upgrade, and super upgrade images to your device.

```

</details>




------------------------------------------------


 ## Thanks
You like this project ? You want to improve this project ? 

Do not hesitate, **Participate**, there are many ways :
- If you don't know bash language you can test releases , and post some issues, some tips and tricks for daily use.
- If you're a coder or a graphist you can fork, edit and publish your modifications with Pull Request on github :)<br/>
- Join my Patreon community and be a part of supporting the development of my various projects!  [![Participate to my Patreon][Patreon-shield]][patreon]
  
- Or you can buy me a coffee to keep me awake during night coding sessions :dizzy_face: !
   <a href="https://www.buymeacoffee.com/schmurtz"><img src="https://www.buymeacoffee.com/assets/img/guidelines/download-assets-sm-2.svg" alt="Buy me a coffee" width="100"/></a>
<br/><br/>

Your contributions make a huge difference in keeping these projects alive !


<br/><br/>

[buymeacoffee-shield]: https://www.buymeacoffee.com/assets/img/guidelines/download-assets-sm-2.svg
[buymeacoffee]: https://www.buymeacoffee.com/schmurtz
[Patreon-shield]:https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white
[patreon]: https://www.patreon.com/schmurtz

 ===========================================================================
 
