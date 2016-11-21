# Slate
# Taming ArchiCAD's floating  palettes with Slate Window Manager.

Hi!

I ended up here looking for a solution in order to keep ArchiCAD's floating palettes under control prior to AC19.  In the Windows version the user is allowed to dock them, that's not the case with the one for Mac OSX and experienced a hard time after been forced to use an Apple Computer.

The following lines are an exctract from the part focused on this issue wich I called project [m] just to give it a name.

# (ch) Monitor Aliases
#———————————————————————————————————

#alias monitor-l
alias monitor-c        1920x1080
alias monitor-r        1920x1200


#ARCHICAD PALETTE DEFAULT LAYOUT ALIASES
#————————————————————————————————————

alias navig           move   screenOriginX;screenOriginY                                    		screenSizeX/5;screenSizeY/2                ${monitor-r}

alias faves           move   screenOriginX;screenOriginY+screenSizeY/2                      		screenSizeX/5;screenSizeY/2                ${monitor-r}

alias trace           move   screenOriginX+(10+screenSizeX/5);screenOriginY                      	288*screenSizeX/1920;202*screenSizeY/1200  ${monitor-r}

alias renov           move   screenOriginX+(10+screenSizeX/5);screenOriginY+(225+10)*screenSizeY/1200 	288*screenSizeX/1920;124*screenSizeY/1200  ${monitor-r}

alias team            move   screenOriginX+(10+screenSizeX/5);screenOriginY+(346+20)*screenSizeY/1200 	288*screenSizeX/1920;364*screenSizeY/1200  ${monitor-r}

alias mark            move   screenOriginX+288*screenSizeX/(1920*5);screenOriginY       		217*screenSizeX/1920;947*screenSizeY/1200  ${monitor-r}


#PROJECT [m] (DEFAULT LAYOUT)
#————————————————————————————————————

layout 2monitor_m 'ARCHICAD':IGNORE_FAIL,MAIN_FIRST,TITLE_ORDER=Favorites;'Trace & Reference';Renovation;Teamwork;'Mark-Up Tools';'Navigator - Project Map';'Navigator - View Map';'Navigator - Layout Book';'Navigator - Publisher Set' ${full-c} | ${faves} | ${trace} | ${renov} | ${team} | ${mark} | ${navig} | ${navig} | ${navig} | ${navig}


#(ch) Layout Bindings
#————————————————————————————————————

bind f3:alt;esc    layout  2monitor_m #MODAL KEY ALT+ESC
#SEEMS LIKE SHIFT+ESC ISN’T FOUND IN STD MAC OS X KEYBOARD SHORTCUTS KEYS AND COULD BE USED AS A MODAL KEY COMBO.
