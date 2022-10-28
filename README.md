FlicFlac 1.11
==================================================

Tiny Portable Audio Converter (WAV FLAC MP3 OGG APE)  

Download binary: <http://sector-seven.com/software/flicflac>

--------------------------------------------------

![FlicFlac](https://raw.githubusercontent.com/DannyBen/FlicFlac/master/Screenshot.png "FlicFlac Screenshot")


Introduction
--------------------------------------------------

This is a simple utility for converting WAV, FLAC, MP3, APE, OGG, M4A and AAC files to
any of the other formats (except M4A and AAC that are only supported as input format).

It uses these external command line encoders/decoders (included in the package):

- [flac.exe (FLAC converter)](http://sourceforge.net/project/showfiles.php?group_id=13478&package_id=12675) - flac-win.zip
- [lame.exe (MP3 converter)](http://www.rarewares.org/mp3-lame-bundle.php#lame-current) - Lame Release Bundle
- [oggenc.exe and oggdec.exe (OGG converter)](http://www.vorbis.com/files/1.0.1/windows/vorbis-tools-1.0.1-win32.zip)
- [MAC.exe (APE converter)](http://www.monkeysaudio.com/)
- [faad.exe (M4A and AAC converter)](https://www.rarewares.org/aac-decoders.php)

If you redistribute this package please refer to the license of these encoders.

On the first run, FlicFlac will create a small INI file for you to do some
minor configurations if needed, and will also save the five needed 
converters into the windows temp directory (flac.exe, lame.exe, oggenc.exe,
oggdec.exe and faad.exe).


Usage
--------------------------------------------------

### Method 1:

- Select a conversion format by pressing one of the format buttons.
- Press the Select button to select files to convert.
  
### Method 2:

- Select a conversion format by pressing one of the format buttons.
- Drag files or folders onto the Select button.
  
### Method 3:

- Drag files or folders onto one of the format buttons.
  
### Method 4:

- Right click a file and select Convert with FlicFlac.
  - This works only on single files.
  - Enable/disable the context menu integration through the settings menu.
  - By default, FlicFlac will exit after conversion when using this method.
    This may be changed in the INI file.
- You may activate the settings menu through the keyboard by pressing F8 or the 
  right click key (apps), or by right clicking anywhere on the GUI.


Technical Notes
--------------------------------------------------

- FLAC files are encoded with the default flac settings (medium compression, 
  medium speed)
- MP3 files are encoded with a default of 192kbps. Encoding mode (CBR/VBR) and
  bitrate are configurable through the INI file.  
  Presets are provided in an easy access menu.  
  Presets menu can be configured in the INI file.  
- OGG files are encoded with a quality setting of 5 (on a scale of 0-10)
- APE files are encoded with a compression level of 2000 (on a scale of 
  1000-2000)
- OGG and MP3 files are encoded with ID3 tag information:    
  Song Title = Filename  
  Year       = Current year  
  Artist     = Taken from the INI file  
- Native Conversions (one step):  
    - **WAV2MP3**   WAV to MP3 (lame)
    - **MP32WAV**   MP3 to WAV  (lame)
    - **FLAC2WAV**  FLAC to WAV (flac)
    - **WAV2FLAC**  WAV to FLAC (flac)
    - **WAV2OGG**   WAV to OGG  (oggenc)
    - **FLAC2OGG**  WAV to FLAC (oggenc)
    - **OGG2WAV**   OGG to WAV  (oggdec)
    - **WAV2APE**   WAV to APE  (mac)
    - **APE2WAV**   APE to WAV  (mac)
    - **M4A2WAV**   M4A to WAV (faad)
    - **AAC2WAV**   AAC to WAV (faad)
- Hybrid Conversions (two steps):
    - **FLAC2MP3**  FLAC to WAV (flac)   then WAV to MP3  (lame) 
    - **FLAC2APE**  FLAC to WAV (flac)   then WAV to APE  (mac) 
    - **MP32FLAC**  MP3 to WAV  (lame)   then WAV to FLAC (flac) 
    - **MP32OGG**   MP3 to WAV  (lame)   then WAV to OGG  (oggenc)
    - **MP32APE**   MP3 to WAV  (lame)   then WAV to APE  (mac) 
    - **OGG2FLAC**  OGG to WAV  (oggdec) then WAV to FLAC (flac)
    - **OGG2MP3**   OGG to WAV  (oggdec) then WAV to MP3  (lame)   
    - **OGG2APE**   OGG to WAV  (oggdec) then WAV to APE  (mac) 
    - **APE2MP3**   APE to WAV  (mac)    then WAV to MP3  (lame) 
    - **APE2OGG**   APE to WAV  (mac)    then WAV to OGG  (oggenc) 
    - **APE2FLAC**  APE to WAV  (mac)    then WAV to FLAC (flac) 
    - **M4A2FLAC**  M4A to WAV  (faad)   then WAV to FLAC (flac)
    - **M4A2MP3**   M4A to WAV  (faad)   then WAV to MP3  (lame)
    - **M4A2OGG**   M4A to WAV  (faad)   then WAV to OGG  (oggenc)
    - **M4A2APE**   M4A to WAV  (faad)   then WAV to APE  (mac) 
    - **AAC2FLAC**  AAC to WAV  (faad)   then WAV to FLAC (flac)
    - **AAC2MP3**   AAC to WAV  (faad)   then WAV to MP3  (lame)
    - **AAC2OGG**   AAC to WAV  (faad)   then WAV to OGG  (oggenc)
    - **AAC2APE**   AAC to WAV  (faad)   then WAV to APE  (mac) 
- MP3 Bitrate Conversion
    - Also supported, MP3 to MP3 - to convert to a different bitrate.


License
--------------------------------------------------

This code is released under the MIT license.
Note that FlicFlac uses external codecs for encoding audio file, please
refer to their respective license.


Contributors
--------------------------------------------------

- [Jastria Rahmat (ijash)](http://www.soundcloud.com/ijash) - icons
  

Change Log
--------------------------------------------------

    2022 10 28 - 1.11
      Updated: MP3 encoder (lame.exe) to version 3.100.1

    2020 04 17 - 1.10
      Added  : Support for AAC and M4A (input only) using faad
      Fixed  : Run as Administrator when enabling/disabling shell integration
      Changed: Links in About dialog
      
    2016 02 27 - 1.03
      Changed: Icon, courtesy of Jastria Rahmat (ijash)
      Changed: License to MIT
      Updated: Some minor code tweaks to support newer AutoHotkey version
      Updated: UI to allow use of Windows theme and act as a tool window
    
    2013 08 16 - 1.02
      Changed: MP3 to MP3 conversion will no longer offer to delete the input file
    
    2011 03 09 - 1.01
      Added  : Support for MP3 to MP3 conversion (bitrate change).
      Changed: About dialog.
    
    2011 01 07 - 1.00
      Added  : Support for Monkey's Audio APE format
    
    2010 12 14 - 0.36
      Fixed  : Shell integration did not work in some cases.
      Updated: Shell integration now sensitive to UAC.
      Changed: Minor GUI changes to better fit Windows 7
      Changed: Default ID3 artist in INI file is now empty
      Updated: Lame MP3 version to 3.98.4
    
    2009 10 06 - 0.32
      Updated: Lame version to 3.98.2.
    
    2009 06 22 - 0.31
      Changed: Recompiled with AutoHotkey 1.0.48.02 due to AVG reporting false
               positive with older AHK version.
    
    2009 06 09 - 0.30
      Added  : Configuration in INI to enable/disable flat buttons. (thanks Dr. 
               Drips).
    
    2008 12 11 - 0.29
      Fixed  : Context menu integration was installed on startup even without user 
               request. Also caused the "Disable Shell Integration" option to be
               temporary, until the next time you use FlicFlac. 
      Removed: "Open folder when done" checkbox. Now resides in the INI file only.
      Added  : "Always on top" checkbox.
      Added  : Option in INI to choose if you want the window to start inactive or
               not, when Always on Top is enabled.
    
    2008 12 09 - 0.28
      Added  : Context menu integration. May be enabled or disabled from the 
               settings menu. Currently supports only single files. No support for 
               multi-files selection or folders.
               When a conversion is done through the context menu, FlicFlac will 
               exit when its done (may be changed in the INI file).
    
    2008 12 03 - 0.27
      Fixed  : Ogg encoders were not cleaned on exit.
      Fixed  : Ogg encoders were not tested for existence.
      Added  : DebugMode - if enabled, will log actions to file and (optionally)
               avoid execution of conversions and deletions.
      Changed: Executables will no longer be oeverwritten in the temp folder. 
               Improves loading time (was broken in 0.26).
      Added  : Temp folder location is now configurable.
      Added  : CleanupOnExit is now configurable (allows to delete the encoders
               on exit).
      Added  : All encoder options are now configurable.
    
    2008 12 03 - 0.26
      Added  : Support for OGG files using OggTools 1.0.1
      Changed: Buttons to flat
    
    2008 08 31 - 0.25
      Changed: Minor maintenance release - removed tray icon.
      
    2008 06 03 - 0.24
      Fixed  : GUI did not look right in some XP theme settings (thanks patto).
      
    2008 06 01 - 0.23
      Added  : Custom dialog boxes for delete confirmation and overwrite 
               confirmation. We will now have "Yes to All" and "No to All" 
               dialogs.
      Added  : The files that were not converted due to a "No" answer to an 
               overwrite confirmation request, will be displayed in a message box
               at the end of the conversion cycle.
      Changed: Default value for ConfirmBeforeDelete key in INI now includes all
               three formats, for consistency (since we now have the yes/no to all
               dialog).
    
    2008 05 31 - 0.22
      Added  : We will now remember the last selected format (thanks Tom de Rooy).
      
    2008 05 30 - 0.21
      Added  : Configuration in INI file to confirm before deleting or overwriting 
               certain file types. By default, we will ask before we delete or
               overwrite FLAC and WAV.
      Added  : A menu for some common operations.
      Added  : Menu item: Open INI. Will start the INI with your default INI 
               editor and wait for you to close it. Then, if it was changed, we 
               will reload ourselves.
      Added  : Sub menu: MP3 encoding presets. The menu elements are completely 
               customizable in the INI file and the last used preset is stored
               in the INI. Selecting "Custom" will use the settings you have
               configured in the INI keys (MP3->Mode, CBRKbps, VBRLevel, VBRRate).
      Changed: When using one of the double conversions (e.g. FLAC2MP3) we will 
               now use a temporary filename for the temporary output instead of
               using the same filename (to avoid accidental overwrite).
      
    2008 05 29 - 0.20
      Added  : Support for FLAC2MP3 conversion (thanks teknocide & Weird Energy).
               This will first do FLAC2WAV then WAV2MP3 since we are using two 
               separate encoders.
      Added  : Support for MP32WAV and MP32FLAC
      Added  : Error message dialog, in case the encoder returns an error code.
               This is done for two reasons: a) to capture bad behavior done by
               the external encoders (e.g. attempting to convert ding.wav at 
               192kbps fails by LAME, but for some reason it still generates an 
               empty MP3 file) and b) to make sure that if we are asked to delete
               the input file, we got a good exit code from the encoder.
      Added  : Some configuration in the INI file to control how we handle errors.
      Added  : Verification code to make sure we have an up to date INI file. In 
               case an INI file from an older version is found, an option to 
               automatically update it is provided.
      Changed: The way we delete source files. Instead of letting the encoder 
               delete the source with a command line switch, we will delete it 
               ourselves if the encoder returned a success exit code. 
               This was changed in order to be more generic (for encoders that do
               not support deletion of input file).
      Changed: Significant changes to internal conversion functions and to the GUI
      Changed: !!! IMPORTANT !!! Delete Input File checkbox is now working the 
               same in all file formats (i.e. we will also delete FLAC and WAV 
               files when it is checked).          
    
    2008 05 28 - 0.14
      Added  : Support for VBR encoding for MP3 (thanks Tom de Rooy).
    
    2008 05 28 - 0.13
      Fixed  : Dragging over non-button control was still attempting to convert.
               No damage was done, since we did not know which conversion to do, 
               but the regex code was inaccurate.
      Added  : Check for correct windows coordinates on startup (was done only on
               shutdown by mistake).
      Added  : The state of the two checkboxes is now also remembered in the INI.
      Added  : Drag and drop support for folders.
      Changed: Some internal code changes.
      Changed: Hot character for the buttons to be consistent (now all are set to
               the target format).
      
    2008 05 28 - 0.12
      Added  : Support for WAV2MP3 conversion, using LAME. 
      Added  : Support for dragging files on the buttons (thanks patto).
      Added  : INI file - to remember last folder, last window coordinates and to
               set MP3 quality and artist ID3 tag.
      Changed: Status text to marquee progress.
      Changed: We will no longer erase the converters executables from the windows
               temporary folder, in order to allow a faster load time.
      
    2008 05 27 - 0.11
      Fixed  : Names with spaces were not supported...
      
    2008 05 27 - 0.10
      Initial Release

