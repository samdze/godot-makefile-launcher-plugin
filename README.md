<p align="middle"><img src="https://i.imgur.com/zXv7H6t.png" /></p>

# Makefile Launcher Plugin
Plugin to execute or build make targets from the Godot Editor.

The plugin adds a new dock to the bottom panel called Make that reads the makefile in your project root directory and creates a list build targets, each triggerable from the UI.

## Installation
- Make sure to have the `make` executable in your PATH.
- Copy the addons/makefile_launcher folder in your addons folder.
- Navigate to Project -> Project Settings -> Plugins and enable the Makefile Launcher plugin.

## How to use
- Place your makefile (or Makefile) in your project root folder.
- Open the Make bottom panel, the plugin will automatically load the build target it finds.
- Click the play icon to the left of a build target to trigger a make build, the output of the make command will appear in the Output panel when it terminates.

![Screenshot](https://i.imgur.com/llZ6kTn.png)

You're free to configure build targets however you like:
- Automations
- Execute scripts
- Build and compile programs
- GDNative development

# Features
- Reload the build targets from the makefile clicking on the refresh icon on the top left.
- Show and hide the Output panel.
- Add optional directives before your make build targets:
  ```makefile
  #confirm
  #args: message branch
  add_commit_push:
    git add .
    git commit -m "$(message)"
    git push origin $(branch)
  ```
  - **#confirm**<br>Require an extra user confirmation before triggering a make build.
  - **#args: <arg_name1> ...**<br>Expose variables to the editor.<br>
    These variables will appear as text fields in the Make panel and can be used during the make build.
