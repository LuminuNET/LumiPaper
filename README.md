LumiPaper
==

Probably not of any use for the public, but here it is anyways!

## License
The PATCHES-LICENSE file describes the license for api & server patches, 
found in `./patches/api` and `./patches/server`.

Everything else is licensed under the MIT license. 
See https://github.com/starlis/empirecraft and https://github.com/electronicboy/byof 
for the license of material used/modified by this project.

## Plugin developers
In order to use Paper as a dependency you must following the steps laid out
in `Building and setting up` and build paper. Each time you want to update
your dependency you must re-build paper.

LumiPaper-API maven dependency:
```xml
<dependency>
    <groupId>net.luminu.paper</groupId>
    <artifactId>paper-api</artifactId>
    <version>1.15.2-R0.1-SNAPSHOT</version>
    <scope>provided</scope>
 </dependency>
 ```
 
 LumiPaper-Server maven dependency:
 ```xml
<dependency>
    <groupId>net.luminu.paper</groupId>
    <artifactId>paper</artifactId>
    <version>1.15.2-R0.1-SNAPSHOT</version>
    <scope>provided</scope>
 </dependency>
  ```

There is no repository required since the artifacts should be locally installed
via building paper.

## Building and setting up
Run the following commands in the root directory:

```
git submodule init
git submodule update
./lumi up
./lumi patch
```

This should initialize the repo such that you can now start modifying and creating 
patches. The folder `LumiPaper-API` is the api repo and the `LumiPaper-Server` folder
is the server repo and will contain the source files you will modify.

#### Creating a patch
Patches are effectively just commits in either `LumiPaper-API` or `LumiPaper-Server`. 
To create one, just add a commit to either repo and run `./lumi rb`, and a 
patch will be placed in the patches folder. Modifying commits will also modify its 
corresponding patch file.


#### Building

Use the command `./lumi build` to build the api and server. Compiled jars
will be placed under `LumiPaper-API/target` and `LumiPaper-Server/target`.
