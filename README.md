# EASYTARGET-ORG laserweb preview

This is a home for an updated version of LaserWeb4, hopefully it is temporary since I would like to see these changes merged upstream.

## [Click here to run the latest version of the Demo in your Browser](https://easytarget-org.github.io/lw-mods-preview/preview/index.html)

These changes live in the *v4.1* branch of my [Fork](https://github.com/easytarget-org/LaserWeb4)
- Note that the branch name changed recently

If you have questions or want to discuss this please [head over to the MakerForums](https://forum.makerforums.info/c/laserweb-cncweb/suggestions-feedback/80)

This update/refresh contains many trivial/layout changes and a few minor functional changes designed to improve the user experience and support modern browser standards.
These changes are mostly UI related, there are *no major or breaking changes to the path generation and gcode rendering parts of the software*, the build environment has also been updated

## LaserWeb4 is a self-contained Webapp
Which means:

### You can run it in your browser with no install required!
Run LaserWeb4 from this repository in your web browser by clicking in the [link](https://easytarget-org.github.io/lw-mods-preview/preview/index.html) above.
- This is a fully functional copy that will allow you to generate and save Gcode via any supported browser (Chrome or Chromium are preferred, but it also works well in FireFox)
- If you have a compatible version of lw.comm-server (v4.1+, dating from January 2022 or later) you can connect to that via the connection panel when in the local network
- Otherwise the connection and machine control tabs will not have any effect, but you can still generate and save gcode for later uploading via your firmware and SD card, or send via LaserGRBL, UGS, Pronterface or whatever

## Changes compared to the current upstream LW4 release
### UI
* Help tooltips added for almost every setting, aimed at new users as well as old hands
* Better presentation and wider choice of preset machine settings, shows wiki/homepage links and logos for predefined firmwares
* Progress indication (% done)
* New gcode info panel showing loaded code status and simulation details when available
  * Simulation shows bounds, time estimates and gcode size summary
* Added a 'Zoom to Gcode' button
  * Added a 5% margin to this and document view
  * The maximum user zoom in on the workspace is increased by 5x, zoom out by 2
* Default filenames for saving gcode and workspaces can be set
  * [strftime()](https://github.com/samsonjs/strftime#supported-specifiers) substitution can be used in them to add date/time stamps.
  * Saved machine settings get the machine ID in the filename
* Better feedback and confirmation for some UI operations, some console logging is improved
* Set the color for workspace and machine bed, plus axis label colors
* Webcam bugfixes; The stream now closes properly and stops when de-selected, copes better with different aspect ratios

#### Operations
* Vertical and reverse-diagonal rastering
* New default settings for burn white and air assist, default segmentation setting
* 'Copy to all operations' is now available on many more fields
* Document re-size tool has slightly larger input boxes (this was really annoying me..)

### Milling
* Mixed-mode machine support, with a specific 'show milling settings' toggle to enable it
* Separate start/end gcode for milling operations (optional)
* New default setting for 'rapid travel height'
* Fluid on/off gcode can be defined

### Import
* The DXF import module has been changed for a more modern one that supports the latest DXF formats and is actively maintained against AutoDesk's continual changes to the 'standard'
  * Support for named layers and text has been lost
  * Support for splines and many modern DXF structures has been added
  * Paths are now grouped by layer color, layers without a color default to black
  * This allows many more files to open successfully with all paths shown, but may make some old files incompatible
    * InkScape can be used to import and convert older files to svg or a more recent DXF version

### Connection
* Support for setting 'ctrl-X on connect' via the connection dialog
* Better behaviour on disconnect/reconnect to running server

### Deveoper stuff
* Weback 5, React 16, Node 16
* Numerous node packages have had updates, and obsolete and unused ones pruned
* Webpack config updated for v5, production buids and devserver working
  * There will be a new developer guide, checked into the reo so it can be kept fresh.

### And More
* Small css changes made to improve Firefox support, I test on Firefox and it *seems*, to run faster than Chrome, ymmv.
* A whole bunch of minor fixes to comments, UI text, dead code, whitespace and trivial bugs.
* I'm still working on this list :smile:

## Known issues
* Modal dialogs (material database amd image vector/filter tool) cannot be closed by clicking the outsde backgrund; use the `[X]` button or `[ESC]` key.
* `npm install` needs the `--force` flag when doing initial install
* I'm still working on this list :frowning:
