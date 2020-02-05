# Compliling StressRefine- Window Visual Studio version
The 4 files bdtranslate.zip, srui.zip, srwithmkl.zip, and SRlibSimple.zip all contain a single
folder with the same name. Each of these is a microsoft visual studio project
that was last modified using
VS2013. That and any newer version should work to compile them.
They are all in C++ except the User interface, srui, which is in C#.
Go in a folder and doubleclick on the ".sln" file to open the project.
If using a newer version than 2013, you may get a message about updating to the latest
VS version,
to which you should say yes.
 
Choose a configuration at the top (debug or release). Next to that it should say x64.
You can change that to win32 but executation is faster in x64 mode.
Now hit build to compile.
A subfolder is created x64/debug or x64/release depending on the configuration.
Inside that folder is the executable, such as SRwithMkl.exe, or in the case of
SRlibSimple, a library file SRlibSimple.lib
SRui is a little different because it is in c#. Also I changed the target name to stressRefine.
There will be a subfolder SRUi, another subfolder bin, then release or debug. inside
will be the executable stressRefine.exe.

Projects SRui, bdftranslate, and SRlibSimple have no external dependencies.

## Linking to libraries
Project srwithmkl depends on SRlibSimple.lib. It also depends on the intel mkl library for
the pardiso solver. You need to specify the right path to these on your machine.
Project/srwithmkl properties/configuration properties

VC++ directores, include directiories is set to 
C:\Program Files (x86)\Intel\Composer XE\mkl\include;$(IncludePath)

VC++ directores, Library Directories is set to
C:\Program Files (x86)\Intel\Composer XE\mkl\include

These are the default locations Intel puts the libraries
when you install the free version of intel mkl.

Now go to  C/C++.
Additional include directories is set to

"libpath"\SRlibSimple\SRlibSimple.
where libpath is the folder for the SRlibSimple project, for example
C:\Users\rich\Documents\Visual Studio 2013\Projects\_SRlib\SRlibSimple\SRlibSimple
If you hit the down arrow and edit a folder browser will come up to select the right folder
Finally under linker/general/additional library directories you need to pick the folder for
SRlibSimple.lib for example:
C:\Users\rich\Documents\Visual Studio 2013\Projects\_SRlib\SRlibSimple\SRlibSimple

I am working on a linux version for these projects, and when available makefiles will be provided
and a new readme file for linux
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc5ODIxNjg5NV19
-->