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
Cachy splash screen - only started showing up on new install (THEY ADDED PLYMOUTH WHYYYYYYYYYYYYYY)


**asdflkjhasdlkjfh**
# To Do
Bug Fixes
	~~Swap to waybar-git (installer)~~
	~~Fix swaync animation (Hyprland config)~~
	~~Fix swaync power button (Swaync config)~~
	~~Fix sleep option (powermenu)~~
	~~~***Fix swaync delay*** (replace with quickshell)~~~
	~~Fix delay between startup and wallpaper loading~~
	~~Fix Hyprlock color change~~
	~~Fix Hyprlock display option~~
Improvements (Back End)
	~~Create separate config files for laptop and desktop setups (Hyprland config, waybar, swaync)~~
	~~Clean up hyprland.lua~~
	~~Break down hyprland.lua into modules~~
	~~Switch to non-trial version of KH Interference~~
New Features
	~~Setup Laptop/Desktop Options (Setup)~~
	Set up GTK themes (Dark preferred)
	Select a cursor (some kind of update to cachy added noctalia)
	~~~Quick settings (Like iOS)~~~
	~~Make 'Fullscreen mode' (Focus Mode)~~
	~~Low power mode~~
	Dark Mode/Light Mode (Swaync menu)
	Workspace view (One day...)
	Touchpad gestures
	Monique?
	Taskbar
	Fastfetch maybe (What's the point of fastfetch)
	


# Known Issues
No consistent themes between GTK applications
~~No input field in Hyprlock~~
~~delay between startup and wallpaper loading~~
~~swaync delay~~
~~Hyprlock color not changing~~
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


Clean up all UI (UI is inconsistent)

reasons:
No text in quick settings, but a bunch of text everywhere else
Menu sizes are inconsistent
Need a proper color scheme


CA