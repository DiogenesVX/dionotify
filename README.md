# dionotify
Audio volume level notification.
This is a small notification utility which shows a nice notification bar when changing the audio volume.
I created it for myself to use with Sway on Debian. If someone finds it useful for his/her situation, I'd be happy :).
Of course this can run basically on any distro and desktop anvironment.



# Features
   1. Get a visual notification bar when changing the audio volume.
   2. Automatically sets maximum volume level to 150%.
   3. Automatically adjusts the volume level to a fixed value (e.g. if the current value is 73, then it will be set to 70).



# Usage
   1. Firstly, for this to work, you need to set the volume increasing/decreasing step by 5, e.g:

          pactl set-sink-volume @DEFAULT_SINK@ +5%
          pactl set-sink-volume @DEFAULT_SINK@ -5%


# Screenshot

![Alt text](https://github.com/DiogenesVX/dionotify/blob/main/dionotify.png)

   
   2. On Sway just put the following lines into your config (I created a folder "dionotify" in ~/.config/sway and put the dionotify script in there):

          bindsym --locked XF86AudioRaiseVolume exec --no-startup-id 'pactl set-sink-volume @DEFAULT_SINK@ +5% && ~/.config/sway/dionotify/dionotify'
          bindsym --locked XF86AudioLowerVolume exec --no-startup-id 'pactl set-sink-volume @DEFAULT_SINK@ -5% && ~/.config/sway/dionotify/dionotify'

   3. Of course you may choose a different key combination or/and location for the script, don't forget to reload Sway configuration afterwards. 

   4. Make sure you have the following packages installed:

          grep
          coreutils
          util-linux
          libnotify-bin
          pulseaudio-utils
