Highlight - In progress
Strikethrough - Complete
Bold & Italics - On hold/Abandoned

Low power mode
- no transparency
- Disable dGPU (If possible)
Performance mode?
# Installer
Laptop/Desktop Option

## Investigate
Cachy splash screen - only started showing up on new install

# To Do
Bug Fixes
	~~Swap to waybar-git (installer)~~
	~~Fix swaync animation (Hyprland config)~~
	~~Fix swaync power button (Swaync config)~~
	~~Fix sleep option (powermenu)~~
	***Fix swaync delay***
	***Fix delay between startup and wallpaper loading***
	~~Fix Hyprlock color change~~
	~~Fix Hyprlock display option~~
Improvements (Back End)
	~~Create separate config files for laptop and desktop setups (Hyprland config, waybar, swaync)~~
	==Clean up hyprland.lua==
	Break down hyprland.lua into modules
New Features
	~~Setup Laptop/Desktop Options (Setup)~~
	Set up GTK themes
	Select a cursor
	~~Make 'Fullscreen mode' (Focus Mode)~~
	Low power mode
	Monique?
	

# Known Issues
No consistent themes between GTK applications
Not input field in Hyprlock
delay between startup and wallpaper loading
swaync delay
Hyprlock color not changing
# Plan
Laptop/Desktop Options

## File Structure

From:
.config
	swaync
		*config.json*
		style.css
	waybar
		*config.jsonc*
		style.css

To:
.config
laptop
	swaync
		*config.json*
		style.css
	waybar
		*config.jsonc*
		style.css
desktop
		swaync
			*config.json*
			style.css
		waybar
			*config.jsonc*
			style.css

## Code
From:
```
# .config/* → ~/.config/*
if [ -d "$REPO_DIR/.config" ]; then
	for item in "$REPO_DIR/.config"/*; do
		name=$(basename "$item")
		backup_and_copy "$item" "$HOME/.config/$name"
	done
else
	warn ".config directory not found in repository environment — skipping."
fi
```

To:
```
if instaltype = 1:
	if laptop files exist:
		backup and copy laptop files to .config
else if installtype = 2:
	if desktop files exist:
		backup and copy desktop files to .config
```

fullscreen mode
+ need to figure out how to do multiple overrides with one keybind
+ also need to close waybar

low power mode
+ activated from swaync
+ battery indicator change color
+ no blur
+ no transparency
+ lower refresh rate
+ lower cpu power