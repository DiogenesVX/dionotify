# dionotify-volume
Audio volume level notification.
This is a small notification utility which shows a nice notification bar when changing the audio volume.
I created it for myself to use with Sway on Debian. If someone finds it useful for his/her situation, I'd be happy :).
Of course this can run basically on any distro and desktop anvironment.

# Features
   1. Get a visual notification bar when changing the audio volume.
   2. Automatically sets maximum volume level to 150%.
   
# Screenshot
   ![Alt text](https://github.com/DiogenesVX/dionotify/blob/main/dionotify-volume.png)

# Usage       
   1. On Sway, just put the following lines into your config (I put the dionotify-volume script into ~/.config/sway):
   
          bindsym --locked XF86AudioRaiseVolume exec --no-startup-id 'pactl set-sink-volume @DEFAULT_SINK@ +5% && ~/.config/sway/dionotify-volume'
          bindsym --locked XF86AudioLowerVolume exec --no-startup-id 'pactl set-sink-volume @DEFAULT_SINK@ -5% && ~/.config/sway/dionotify-volume'
          
  Of course you may choose a different key combination or/and location for the script, don't forget to reload the Sway configuration afterwards. 
   
   2. Make sure you have the following packages installed:
   
          grep
          coreutils
          util-linux
          libnotify-bin
          pulseaudio-utils
