# Generating docs using DocFX

Documentation is generated using the DocFX tool. If you wish to understand everything clearly it is heavily recommended to read [the DocFX manual](https://dotnet.github.io/docfx/tutorial/docfx.exe_user_manual.html).
In the file structure seen below, the DocFxConfig folder is the result of running
```
docfx init -q
```  
This command will create a folder with an identical structure to DocFxConfig, however some of the contents in docfx.json have been changed to redirect the output of the tool to the static folder (see figure below).

Cloning this repository will ensure you have the correct file structure and modifications to various files (mainly docfx.json, the addition of filterConfig.yml, and the files under articles ).

You can read more about what the docfx.json changes mean, and all about docfx [here](https://dotnet.github.io/docfx/tutorial/docfx.exe_user_manual.html).

Simply put, documentation files are  generated by locating whatever we want to be documented under the src folder. In our case, 
we have a copy of the [Unity Framework](https://github.com/Fizzyo/FizzyoFramework-Unity).

(Note this repo has an empty src, please copy the framework if you wish to use the tool)

Additionally, all of the files found in the articles tab are located inside the articles folder. You can find a copy of these in the articles section of the directory. 

Now, to generate the documentation we run the following command inside the DocFxConfig directory:

```
# pwd = ~/DocFxConfig/

# If on Windows
docfx/docfx.exe build
 
# If on Linux
mono docfx/docfx.exe build
```
Thanks to the configuration specified in the docfx.json file, all of the generated files will be placed 
under the static folder, as seen in the figure below. 

And thats it! The [documentation site](http://dev.fizzyo-ucl.co.uk) is serving files in static folder.

If you wish to serve the files locally run the following command instead: 
```
# pwd = ~/DocFxConfig/

# If on Windows
docfx/docfx.exe serve
 
# If on Linux
mono docfx/docfx.exe serve
``` 

# Installing DocFX

Make sure to unzip the contents of DocFxConfig/docfx/docfx.zip to unpack the executable and all files needed to run the tool.
Additionally if working on Linux, mono is required to run DocFX. Follow the steps found [here](https://github.com/dotnet/docfx/issues/718#issuecomment-256700598).

# File structure

```
+-- DocFxConfig
|   +-- api
|   +-- apidoc
|   +-- articles
|   +-- docfx
|   |   +-- docfx.exe 
|   |   +-- ...
|   +-- docfx.json
|   +-- filterConfig.yml
|   +-- images
|   +-- index.md 
|   +-- obj
|   +-- src
|   +-- toc.yml
+-- static  # Files being served
|   +-- index.html
|   +-- ...
+
```