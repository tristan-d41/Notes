Low power mode
- no transparency
- Disable dGPU (If possible)
Fullscreen mode
- Hide waybar
- No gaps
- No rounding
Performance mode?
# Installer
Laptop/Desktop Option

# To Do
~~Swap to waybar-git (installer)~~
***Setup Laptop/Desktop Options (Setup)***
Fix swaync animation (Hyprland config)
Fix swaync power button (Swaync config)
Create separate config files for laptop and desktop setups (Hyprland config, waybar, swaync)
Fix sleep option (powermenu)

# Known Issues
No consistent themes between GTK applications
~~Swaync animation goes the wrong way~~
Swaync is *slow*
~~Powermenu has an unused option (Logout)~~
Hyprlock color doesn't change
Delay between startup and wallpaper loading

# Plan
Laptop/Desktop Options

## File Structure

.config
	swaync
		*config.json*
	waybar
		*config.jsonc*
	