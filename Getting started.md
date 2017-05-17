
# Getting started

## Get myou-tool

* Install node.js
* Open a terminal and type:

`npm install -g myou-tool`

(on Linux you probably need to add `sudo` at the beginning)

Myou-tool comes with everything necessary to start a project except for Blender.

## Get Blender

Blender is not strictly necessary to use Myou Engine, but it is very recommended since it doubles up as a WYSIWYG editor.

Supported versions include:

* [Blender 2.78](https://www.blender.org/) onwards for "Blender internal" and "Blender game" render engines (recommended option for now).
* [Blender PBR branch](http://www.clement-foucault.com/#blender_pbr) for "Cycles" materials, more realistic and flexible but more resource intensive in some cases.
* Blender 2.71 for legacy reasons (will be deprecated).

Support for other 3D formats and applications will come soon.

## Install the Blender add-on

Run this command:

`myou-tool install addon`

It will try to detect your installed Blender version, but if it fails you can always supply one or more versions:

`myou-tool install addon 2.78`

Then enable the addon in Blender by following these steps:

* File -> User Preferences... -> Add-ons -> Game Engine
* Click the checkbox next to "Myou game engine"
* Click Save User Settings

## Create a project

Run this command:

`myou-tool init testProject`

Replace `testProject` by the name of the folder you want to create it in. If the folder doesn't exist it will be created. If you omit the folder it will assume the current folder (similar to git init and npm init).

It will create a NPM `package.json` file for you if it doesn't exist already, then it will install dependencies and copy the files of a basic template project.

## Run the project

Enter the folder by typing

`cd testProject`

and run:

`npm start`

This starts two commands in one: `myou-tool server webpack --watch`
which creates a development web server and [webpack](https://webpack.js.org/) in watch mode.

Open http://localhost:8000/ in your browser.

## Modify the code

Open `main.coffee`.

(TODO: very simple addition here)

See [Start up](Tutorials/Start up.md) for details on what this code does.

See [Moving things around](Tutorials/Moving things around.md) for details.

## Open the 3D assets

Open `data.blend` in Blender. To preview WYSIWYG materials do the following

### For Blender internal/Blender game

* Select the appropiate render engine in the drop down box at the top.
* Open the properties panel at the right of the 3D view ('+' icon or press the N key while the pointer is inside the 3D view).
* Scroll down to the *Shading* section.
* Change the mode from *Multitexture* to **GLSL**
* Materials will then be previewed when in **Textured** viewport shading mode (drop down box next to "object mode" below the 3D view).
* All these changes are preserved in the .blend file.

### For Blender PBR branch

* Select **Cycles** render engine in the drop down box at the top.
* Open the properties panel at the right of the 3D view ('+' icon or press the N key while the pointer is inside the 3D view).
* Scroll down to the *Shading* section.
* Ensure the **Material Preview** checkbox is enabled.
* Materials will then be previewed when in **Material** viewport shading mode (drop down box next to "object mode" below the 3D view).
* All these changes are preserved in the .blend file.

## Modify the 3D assets

* Make some changes.
* Go to the myou export panel in the render tab.
* Select the export path and export name here. You don't need to select it every time.
* Click the big Export button. The first time may take longer than usual, esp. with a big amount of meshes and textures. Subsequent exports are much faster due to caching.
