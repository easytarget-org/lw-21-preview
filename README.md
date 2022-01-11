# EASYTARGET-ORG laserweb preview

This is a home for an updated version of LaserWeb4, hopefully it is temporary since I would like to see these changes merged upstream.

## [Click here to run the latest version of the Demo in your Browser](https://easytarget-org.github.io/lw-mods-preview/preview/index.html)

This update/refresh contains many trivial/layout changes and a few minor functional changes designed to improve the user experience.
Mostly UI related, there are *no major or breaking changes to the path generation and gcode rendering parts of the software*.

## LaserWeb4 is a self-contained Webapp
Which means:
### You can run it in your browser with no install required!
Run LaserWeb4 from this repository in your web browser by clicking in the [link](https://easytarget-org.github.io/lw-mods-preview/preview/index.html) above.
- This is a fully functional copy that will allow you to generate and save Gcode via any supported browser (Chrome or Chromium are preferred, but it also works well in FireFox)
- If you have a compatible version of lw.comm-server (v4.1+, dating from January 2022 or later) you can connect to that via the connection panel when in the local network.
- Otherwise the connection and machine control tabs will not have any effect, but you can still generate and save gcode for later uploading via your firmware and SD card, or with LaserGRBL, UGS, Pronterface or any other gcode file streamer.

## Changes compared to the current upstream LW4 release

### UI
* Help tooltips for almost every setting
* Better presentation and wider choice of preset machine settings
* Gcode info panel showing loaded code status and simulation details when available
  * Simulation shows bounds, time estimates and gcode size summary
* Default filenames for saving gcode and workspaces can be set; [strftime()](https://github.com/samsonjs/strftime#supported-specifiers) substitution can be used in them to add date/time stamps.
* Better feedback and confirmation for dangerous commands, some console logging is improved
* Support for setting 'ctrl-X on connect' via the connection dialog
* Webcam bugfixes; it now closes properly (both window and stream) when de-selected

#### Operations
* Vertical and reverse-diagonal rastering
* New default settings for burn white and air assist
* 'Copy to all operations' is now available on many more fields
* Document size tool has slightly larger input boxes

### Milling
* Mixed-mode machine support, with a specific 'show milling settings' toggle to enable it
* Separate start/end gcode for milling operations (optional)
* New default setting for 'rapid travel'
* Fluid on/off gcode can be defined

### Import
* The DXF import module swapped for a more modern one that supports the latest DXF formats
  * Support for layers and text has been lost.
  * Support for splines and many modern DXF structures has been added.
  * Paths are now grouped by color.
  * This allows many more files to open successfully with all paths shown, but may make some old files incompatible.

### And More
* A whole bunch of minor fixes to comments, dead code, whitespace and trivial bugs. 
* I'm still working on this list
