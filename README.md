# i3scrot
simple command-line utility to take screenshots on i3wm. 
can upload the screenshot to an image hosting service for easy sharing.

## Installation
```bash
git clone https://github.com/sh7ven/i3-screenshot
cd i3-screenshot
./install.sh
```

## Usage
```
USAGE: ./i3scrot [TYPE] [OPTIONS]

TYPE:
--window 	-w		-- capture a particular window.
--full		-f		-- capture the entire screen. (:0)
--selection	-s		-- select a rectangle to capture.


OPTIONS:
--upload 	-u		-- upload the image to a hosting service for easy sharing.
--service			-- (TODO) image hosting service
--verbose	-v 		-- make the curl operations verbose
```

## Examples
take a screenshot of the entire screen and upload it:
```
./i3scrot --full --upload
./i3scrot  -f     -u
```

take a screenshot of a selection, and be verbose:
```
./i3scrot --selection --verbose
./i3scrot  -s          -v
```

## With `i3`
```i3config
~/.config/i3/config
-------------------

bindsym Print       exec --no-startup-id /usr/bin/i3scrot -f
bindsym Alt+Print   exec --no-startup-id /usr/bin/i3scrot -w
bindsym Shift+Print exec --no-startup-id /usr/bin/i3scrot -s
```

## TODOs
- a GUI + daemon
- multi monitor
- curl flags (secret, retention time etc)
- support for different image hosting services
