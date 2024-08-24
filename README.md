# theme-for-i3wm-and-polybar
This is a simple script that allows you to easily change and save your current i3 and polybar theme and settings.
# Usage:
To set a theme, run the script with ''./theme set (theme-name)''. This will copy the configuration files inside the ~/themes/(theme-name) directory to the i3 and polybar configuration.

To save a theme, run the script with ''./theme save (theme-name)''. This will copy the i3 and polybar config into the ~/themes/(theme-name) directory.

Feel free to change anything on the script :)



#code:

#!/bin/bash

theme=$2

if [ "$1" = "set" ]; then

        cp "$HOME/themes/$theme/polybar" "$HOME/.config/polybar/config.ini"

        cp "$HOME/themes/$theme/i3" "$HOME/.config/i3/config"

elif [ "$1" = "save" ]; then

        mkdir "$HOME/themes/$theme" 

        cp  "$HOME/.config/polybar/config.ini" "$HOME/themes/$theme/polybar"

        cp  "$HOME/.config/i3/config" "$HOME/themes/$theme/i3"
fi
