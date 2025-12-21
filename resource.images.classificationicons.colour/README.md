
## ABOUT resource.images.classificationicons.colour
Provides a collection of square aspect ratio video classification icons from around the world. This is my attempt to set a standard to provide classification icon images for use in Kodi media centre skins.
By providing a standard naming scheme for the images it is my hope that this will become the standard way for Kodi skins to support more than a tiny subset of available classification icons.


## NAMING SCHEME:

Icons in this colletion are named using the following rules:

[Country Name]{ (Region)}[ {TV-}Classification].png

[] - Required
{} - Optional

* Country Name Can contain spaces but uses Camel code for naming. For example New Zealand. Required part of filename, uses English country name.
* Region Not required but if used must also not contain spaces and must be surrounded by brackets. For example Canada (Quebec) if using classifications from Quebec.
* TV- For if country has a seperate classification scheme for TV broadcasts. A lot of countries do not use a seperate classification scheme for Movies and TV, thus is not required.
* Classification Once again the English version of the text used to describe classification.
* .png Images are png's and thus required ListItem.Mpaa field will contain everything above minus the .png

So using the above scheme an example would be as follows:

Australia TV-C.png as file name in this file and Australia TV-C as the required text in ListItem.Mpaa

Using the above scheme allows a number of benefits, those include:

* ListItem.Mpaa field is still human readable, so skins that do not provide classification icons can still display reasonable looking text for the classification.
* Icons can be displayed using a simple image control, thus can be displayed rapidly.
* Skin writer does not have to keep adding code to their skin to support additional countries classification codes.
* Current method to display classification codes does not scale. Each new country requires adding further variable code (slows Kodi down with each new addition).
* Currently does not seem to be a universal naming scheme and thus only a very small subset of counties have icons provided, often skins only provide a limited number of different icons.
* Old naming scheme sometimes used a : character, which is an illegal character in some filesystems. This required the skin to translate the ListItem.Mpaa string to something file system friendly.

Unfortunately you can't bake a cake without breaking a few eggs. The following issues will need to be addressed:

* Current scrappers do not follow this standard, they will require a rewrite to make this seemless to the users.
* Current users will need to either rescrape with new scrappers or use a converstion script to comply with new scheme. Alternately they will need to edit their libraries in some way.

## CODE:

The following code can be used to access the icons in the resource file. The code consists of one Image control and thus is very quick. Additional code can be used to provide fallback for old method of icon display.

		<control type="image"><!-- Classification Rating (quick way) -->
			<left>1796</left>
			<top>56</top>
			<width>64</width>
			<height>64</height>
			<align>right</align>
			<aligny>bottom</aligny>
			<texture fallback="resource://resource.images.classificationicons.colour/Check Classification.png">$VAR[MPAARatingIcons]</texture>
			<aspectratio>keep</aspectratio>
			<visible>$EXP[isnotEmptyDBID]</visible>
		</control>

	<variable name="MPAARatingIcons">
		<value condition="Skin.HasSetting(defaultmpaa-locale)">$INFO[Listitem.MPAA,resource://resource.images.classificationicons.colour/,.png]</value>
		<value condition="!Skin.HasSetting(defaultmpaa-locale)">$INFO[Window(home).property(locale.country),
		resource://resource.images.classificationicons.colour/] $INFO[Listitem.MPAA,,.png]</value>
	</variable>

Variable code above not strictly required, but does allow for the user to stick with United States certification over their local region if required.

## CONVERTING TO NEW SCHEME:

Unfortunately the new naming scheme is not really compatible with the old scheme and thus will require the user to make changes to their video database.
The suggested way to convert to the new scheme include:

* Use the Universal movie scrapper. Under the scrappers configuration settings 'Ratings' change to your prefered certification country to your required country.
  Then change the certification prefix setting to required country followed by a space. Rescrape your video library. Slow and only applies to movie library. (Don't need to use certification prefix as this is now provided automagically)
* Export your library to seperate .nfo files and then edit MPAA entry of each file. Slow and tedious, but does get the job done.
* Making use of an external library managment program to edit MPAA entries to use new scheme. I have not used these types of programs so have nothing to say on their usefulness.
* Hopefully I can convince a script writer to write a script to bulk convert to new naming scheme. This has the best potiential to provide a seemless transition to new system. Fingers crossed. ( Nope, no takers. Have made minors changes to allow for this. )
* And finally, the scrapper writters see the value of new scheme and update their scrappers to suit.

## ADDENDUM TO ABOVE POINT:

The previous section does not reflect the current state of this scheme as a number of skin and script writers pointed out a number of issues, these include.

* A number of skins do not use icons for MPAA certification ratings and were not open to including additional information in the Listitem.MPAA field as it would mess with text field formatting in their skins.
* Users where unlikely to run a script to shift to new scheme. An automagical system was required to encourage user uptake. Also I was unable to find a script writer willing to write a script for the conversion.

With the above in mind I have made a number of minor changes to scheme to address previous issues. While the file naming scheme of the resource file has NOT changed, the way to access the file as a skin writer has. Scheme no longer requires the region to be included in the Listitem.MPAA info string. Thanks to Sulafred (writer of Embuary skin and Emburary skin helper script) a way has been provided to access the users locale country via a helper script in Kodi Leia and Kodi Matrix provides this thru the skin engine. Using this information, the skin writer can provide a string to access the correct file from the provided resource file. Sulafred's Metadata Editor (or other library editing script if the user prefers) can provide a way for the user to edit individule library entries that don't match. So for the most part solution is automagical.

## SUPPORTED COUNTRIES:

The following countries are currently supported, hopefully more to follow.

* Australia
* Australia TV
* Belgium (New)
* Brazil
* Canada
* Canada TV
* Denmark
* Finland
* France TV
* Germany
* Germany TV (New)
* Ghana (New)
* Greece (New)
* Hong Kong
* Hungary
* Hungary TV
* Iceland (New)
* India
* Ireland
* Italy (New)
* Japan
* Kenya (New)
* Korea
* Korea TV
* Malaysia (New)
* Maldivies (New)
* Netherlands
* New Zealand
* Nigeria (New)
* Norway
* Philippines (New)
* Poland (New)
* Portugal
* Russia
* Saudi Arabia (New)
* Singapore (New)
* Slovakia (New)
* South Africa (New)
* South Korea (New)
* Spain
* Switzerland (New)
* Taiwan
* Thailand (New)
* Turkey (New)
* UAE (New)
* United Kingdom
* United States
* United States TV
* Vietnam

In addition I have provided a Check Classification icon and have duplicated the United States and United States TV set of icons as Rated and TV- to allow for the old naming scheme.
The United States icons under the old scheme could also contain the : character, which is an illegal character under some file systems, so they have not been provided.

## NOTE:

All icons provided have been sourced from various locations around the web (mainly from this wikipedia article https://en.wikipedia.org/wiki/Motion_picture_content_rating_system#).
The icons have been processed to meet my requirements of 64 x 64 pixle .png files, so may or may not be exact duplicates of existing files. They are provided as is under the fair use
provisions of copyright law. If you feel that your icons have been used in error, please contact me thru my GitHub e-mail address and I will endeavor to correct the issue.

## FINALLY:

As the resource currently stands it provides a fast way to access a large number of different country certification icons. It also allows for the rapid addition of countries without the need to update supporting skins. If your country is not currently supported and you have square aspect images of the certification icons, contact Wyrm via the Kodi forums and they will be added. Also the scheme allows for alternate naming of certification icons, so if icon is present but the Listitem.MPAA field returns an alternate naming for the icon, please contact Wyrm to correct issue.

## DEVELOPMENT:
[Github](https://github.com/wyrm65/resource.images.classificationicons.colour)

