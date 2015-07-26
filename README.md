### QREencode Compilation on Windows (32 bits)
Executable runs on 32 bits and 64 bits.

To compile, requires the CygWin Environment (Unix/Linux Environment on Windows).

*See document "CygWin on Windows 32 - How To" for details on how to install CygWin.*

<br>

##### The 3 general steps needed to compile (simplified):
> ./configure

> make

> make install


##### Actual steps that I did:
> ./configure --prefix=/myDestination/FolderOf/Binary/  --enable-static  --disable-shared

> make

> make install

The resulting standalone (portable) binary will be on the */myDestination/FolderOf/Binary/***bin/** folder.

The executable file is "**QREncode.exe**".

<br>
##### Executing on a machine **without** CygWin installed:
Need to include some modules (.dlls) on the same folder that you want the executable (QREncode.exe) to be.

These are the files that I did included:
> 1) cygwin1.dll

> 2) cygz.dll

> 3) cyggcc_s-1.dll

> 4) cygpngNN-NN.dll  (NN is a number, see the "ldd" command below)

> 5) qrencode.exe  (this is the main executable)

<br>
##### Use "ldd" command to know what files are needed:
> ldd  qrencode.exe

Shows a list of components that the executable need to run.

> In my case, I did copy the "**cygpng16-16.dll**"

<br>
#### Full HowTo - Compiling QREncode on Windows 32 bits.

a) Donwload and extract the QREncode source code.
> 1) tar  -xzvf  qrencode3.4.4.tar.gz

b) Enter the directory of the source code.
> 2) cd  qrencode3.4.4

c) Execute the configuration step.
> 3) configure  --prefix=/home/myfolder/  --enable-static  --disable-shared

d) Compile.
> 4) make

e) Install the executable in your desired folder.
> 5) make install

f) Run the "ldd" command to know what files are needed to execute portable...
> 6) ldd qrencode.exe

g) Place the executable (qrencode.exe) and all the needed components inside a new folder, this will be the portable folder.

<br>

##### Downloading the QREncode Source Code:
Please, get the source code form the Kentaro Fukuchi website: http://fukuchi.org/works/qrencode/

<br>

##### Install CygWin (32 bits) on Windows
To make things simple, I did install CygWin including the following 2 CATEGORIES of soft:

> Base

> Devel

These 2 are enough to compile the QREncode.
<br>



