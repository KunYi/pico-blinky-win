Raspberry Pi Pico on Windows development environment
===

the repository for Raspberry Pi Pico (RP2040) developement on Windows
use PowerShell with Visual Studio 2022

need modify **envsetup.ps1** to match your build environments

verify with pico-sdk v1.3

we need install the below software items

* cmake 3.13 and later
* pico-sdk 1.3
* python 3.6 and later
* visual studio 2015 and later
* ninja

The following is operation log
```
Windows PowerShell
Copyright (C) Microsoft Corporation. All rights reserved.

Try the new cross-platform PowerShell https://aka.ms/pscore6

PS C:\Users\kunic\source\repos\pico\blinky> .\envsetup.ps1
**********************************************************************
** Visual Studio 2022 Developer PowerShell v17.1.0
** Copyright (c) 2021 Microsoft Corporation
**********************************************************************
PS C:\Users\kunic\source\repos\pico\blinky> mkdir build


    Directory: C:\Users\kunic\source\repos\pico\blinky

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          3/3/2022   1:13 PM             build


PS C:\Users\kunic\source\repos\pico\blinky> cd build
PS C:\Users\kunic\source\repos\pico\blinky\build> cmake -G "Ninja" ..
Using PICO_SDK_PATH from environment ('C:\Users\kunic\source\repos\pico\pico-sdk')
PICO_SDK_PATH is C:/Users/kunic/source/repos/pico/pico-sdk
Defaulting PICO_PLATFORM to rp2040 since not specified.
Defaulting PICO platform compiler to pico_arm_gcc since not specified.
-- Defaulting build type to 'Release' since not specified.
PICO compiler is pico_arm_gcc
-- The C compiler identification is GNU 10.3.1
-- The CXX compiler identification is GNU 10.3.1
-- The ASM compiler identification is GNU
-- Found assembler: C:/Program Files (x86)/GNU Arm Embedded Toolchain/10 2021.10/bin/arm-none-eabi-gcc.exe
Defaulting PICO target board to pico since not specified.
Using board configuration from C:/Users/kunic/source/repos/pico/pico-sdk/src/boards/include/boards/pico.h
-- Found Python3: C:/Python310/python.exe (found version "3.10.0") found components: Interpreter
TinyUSB available at C:/Users/kunic/source/repos/pico/pico-sdk/lib/tinyusb/src/portable/raspberrypi/rp2040; enabling build support for USB.
-- Configuring done
-- Generating done
-- Build files have been written to: C:/Users/kunic/source/repos/pico/blinky/build
PS C:\Users\kunic\source\repos\pico\blinky\build> ninja
[9/59] Performing configure step for 'ELF2UF2Build'
-- The C compiler identification is MSVC 19.31.31104.0
-- The CXX compiler identification is MSVC 19.31.31104.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: C:/Program Files/Microsoft Visual Studio/2022/Professional/VC/Tools/MSVC/14.31.31103/bin/Hostx86/x86/cl.exe - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: C:/Program Files/Microsoft Visual Studio/2022/Professional/VC/Tools/MSVC/14.31.31103/bin/Hostx86/x86/cl.exe - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: C:/Users/kunic/source/repos/pico/blinky/build/elf2uf2
[10/59] Performing build step for 'ELF2UF2Build'
[1/2] Building CXX object CMakeFiles\elf2uf2.dir\main.cpp.obj
C:\Users\kunic\source\repos\pico\pico-sdk\tools\elf2uf2\main.cpp(331): warning C4996: 'fopen': This function or variable may be unsafe. Consider using fopen_s instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.
C:\Users\kunic\source\repos\pico\pico-sdk\tools\elf2uf2\main.cpp(337): warning C4996: 'fopen': This function or variable may be unsafe. Consider using fopen_s instead. To disable deprecation, use _CRT_SECURE_NO_WARNINGS. See online help for details.
[2/2] Linking CXX executable elf2uf2.exe
[59/59] Linking CXX executable blinky.elf

```
