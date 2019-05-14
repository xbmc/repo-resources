
## ABOUT resource.images.classificationicons.colour
Provides a collection of square aspect ratio video classification icons from around the world. This is my attempt to set a standard to provide classification icon images for use in Kodi media centre skins.
By providing a standard naming scheme for the images it is my hope that this will become the standard way for Kodi skins to support more than a tiny subset of available classification icons.
  

## NAMING SCHEME:

Icons in this colletion are named using the following rules:

[CountryName]{(Region)}[ {TV-}Classification].png

[] - Required
{} - Optional

* CountryName Contains NO spaces but uses Camel code for naming. For example NewZealand NOT New Zealand. Required part of filename, uses English country name.
* Region Not required but if used must also not contain spaces and must be surrounded by brackets. For example Canada(Quebec) if using classifications from Quebec.
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

	<control type="group">
		<visible>$EXP[isnotEmptyDBID]</visible>
		<control type="image" id="4550">
			<!-- Classification Rating (quick way) -->
			<left>36</left>
			<top>414</top>
			<width>64</width>
			<height>64</height>
			<aligny>bottom</aligny>
			<texture fallback="blank.png">$INFO[ListItem.Mpaa,resource://resource.images.classificationicons.colour/,.png]</texture>
			<aspectratio>keep</aspectratio>
		</control>
		<control type="image">
			<!-- Classification Rating -->
			<left>36</left>
			<top>414</top>
			<width>64</width>
			<height>64</height>
			<aligny>bottom</aligny>
			<texture>$VAR[ClassificationRating]</texture>
			<aspectratio>keep</aspectratio>
			<visible>String.IsEqual(Control.GetLabel(4550),blank.png)</visible>
		</control>
	</control>

## CONVERTING TO NEW SCHEME

Unfortunately the new naming scheme is not really compatible with the old scheme and thus will require the user to make changes to their video database.
The suggested way to convert to the new scheme include:

* Use the Universal movie scrapper. Under the scrappers configuration settings 'Ratings' change to your prefered certification country to your required country.
  Then change the certification prefix setting to required country followed by a space. Rescrape your video library. Slow and only applies to movie library.
* Export your library to seperate .nfo files and then edit MPAA entry of each file. Slow and tedious, but does get the job done.
* Making use of an external library managment program to edit MPAA entries to use new scheme. I have not used these type of programs so have nothing to say on their usefulness.
* Hopefully I can convince a script writer to write a script to bulk convert to new naming scheme. This has the best potiential to provide a seemless transition to new system. Fingers crossed.
* And finally, the scrapper writters see the value of new scheme and update their scrappers to suit.

## SUPPORTED COUNTRIES

The following countries are currently supported, hopefully more to follow.

* Australia
* Australia TV
* Brazil
* Canada
* Canada TV
* Canada(Quebec)
* Denmark
* Finland
* France TV
* Germany
* Hungary
* India
* Ireland
* Italy
* Japan
* Netherlands
* NewZealand
* Russia
* SouthKorea
* SouthKorea TV
* Spain
* UK
* USA
* USA TV

In addition I have provided a Check Classification icon and have duplicated the USA and USA TV set of icons as Rated and TV- to allow for the old naming scheme.
The USA icons under the old scheme could also contain the : character, which is an illegal character under some file systems, so they have not been provided.
## DEVELOPMENT:
[Github](https://github.com/wyrm65/resource.images.classificationicons.colour)

