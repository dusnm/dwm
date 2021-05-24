# My build of dwm (Dynamic Window Manager)

In my humble opinion the defaults dwm comes with are completely unusable, hence this is yet another patched version among many.

### Included patches

-   **alwayscenter** (centers floating windows)
-   **restartsig** (restarts dwm with a keybinding)
-   **attachbottom** (attaches new windows to the bottom of the stack, instead of to the top)
-   **fullgaps** (adds useless gaps for aesthetics)
-   **monoclesymbol** (makes the monocle symbol always appear in statusbar)
-   **scratchpad** (adds a hidden terminal "scratchpad" that can be pulled up with a keybinding)
-   **statusallmons** (displays the statusbar on all monitors)
-   **warp** (warps the mouse cursor when switching tags)

### Additional dependencies

-   **alacritty** (instead of st)
-   **my shell scripts** (for functionality such ash the volume indicator)
-   **Jetbrains Mono** (default font)
-   **font-awesome** (icon font)

### Requirements

In order to build dwm you need the Xlib header files.

### Installation

Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install

### Running dwm

Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm

### Configuration

The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
