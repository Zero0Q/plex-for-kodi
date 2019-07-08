Official Modified Plex addon for Kodi.

The feature changes are:
https://aws1.discourse-cdn.com/plex/optimized/3X/1/4/14f19288900b5018414e927ed758d067fe14633d_2_690x388.jpeg
https://aws1.discourse-cdn.com/plex/optimized/3X/b/6/b64b0bd6107d9cc099ded7df203e1c5f0a1549c9_2_690x368.jpeg

Massive UI changes and additions.
Support marking as watched for external players (important for windows using madvr). Item gets scrobbled after 5 mins.
This may be in conflict with desired behavior if you are using internal player and wish to use resume support.
Exiting plex now exits Kodi.
Actual filename being played gets stored in c:\htpc\plexapi folder if this exists. If not, nothing happens with this.
This feature is useful for scripts that may want to do some things based on the real filename
Libraries can be filtered from plex for kodi now by renaming the library to something with ‘-’ in the name.
So if you dont want to see music, change it to music- and it won’t show up in this interface.
All my testing has been done using external players as that’s my only use for plex for kodi on my HTPC.

Installation
There are a few steps required to install this updated version of plex.

Install plex for kodi addon from video repository and make sure it’s working in plex.

Recommended to wipe out kodi library entirely and configure plex to load as a service.
This will allow kodi to just become plex and to get into plex within 1 second of load.

Recommend use estuary as theme.

To install updated addon, we will use the install folder addon at c:\program files (or wherever you installed kodi).
Copy this folder (script.plex) to c:\program files\kodi\addons
Delete %appdata%\kodi\addons\script.plex

Copy teh fonts file. If you’re using estuary default theme, then just copy script.plex\Fonts.xml to c:\program files\kodi\addons\skin.estuary\xml\ and overwrite the Fonts.xml file there.

Or you can modify your fonts file yourself if you are not using estuary. The path to that skin is something like:
c:\program files\kodi\addons\skin.estuary\xml.

Specifically we need definitions for font06, font08, and font09. See the lines added to estuary’s font.xml:

<---------- cut here ----------->

Copy to clipboard
	<font>
		<name>font06</name>
		<filename>NotoSans-Regular.ttf</filename>
		<size>14</size>
		<style>lighten</style>
	</font>
	<font>
		<name>font08</name>
		<filename>NotoSans-Regular.ttf</filename>
		<size>18</size>
		<style>lighten</style>
	</font>
	<font>
		<name>font09</name>
		<filename>NotoSans-Regular.ttf</filename>
		<size>20</size>
		<style>lighten</style>
	</font>
<---------- cut here ----------->

Otherwise the title and description will be blown out too big.

Please PR contributions against the `develop` branch.
