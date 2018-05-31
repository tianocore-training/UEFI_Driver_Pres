---?image=assets/images/gitpitch-audience.jpg
@title[UEFI_Driver_Pres]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### How to Write a UEFI Driver

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  UEFI Driver Model and Driver Wizard Pres

  Copyright (c) 2018, Intel Corporation. All rights reserved.<BR>

  Redistribution and use in source (original document form) and 'compiled'
  forms (converted to PDF, epub, HTML and other formats) with or without
  modification, are permitted provided that the following conditions are met:

  1) Redistributions of source code (original document form) must retain the
     above copyright notice, this list of conditions and the following
     disclaimer as the first lines of this file unmodified.

  2) Redistributions in compiled form (transformed to other DTDs, converted to
     PDF, epub, HTML and other formats) must reproduce the above copyright
     notice, this list of conditions and the following disclaimer in the
     documentation and/or other materials provided with the distribution.

  THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR
  IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
  MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
  EVENT SHALL TIANOCORE PROJECT  BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
  SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO,
  PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS;
  OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY,
  WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR
  OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF
  ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.



---  
@title[Lesson Objective]
<BR>
### <p align="center"<span class="gold"   >Lesson Objective </span></p><br>

<!---  Add bullets using https://fontawesome.com/cheatsheet certificate
-->
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;What is the UEFI Driver Model</span> </li><br>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Setup the UEFI Driver Wizard</span></li><br>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Create a UEFI Driver Template</span> </li>
</ul>

---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Driver Model]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Model </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>



---?image=/assets/images/slides/Slide4.JPG
<!-- .slide: data-transition="none" -->
@title[Defining a UEFI Driver?]
<p align="right"><span class="gold" >Defining a UEFI Driver?</span></p>

Note:

- An UEFI Loadable Image
- May produce or consume protocols
- Protocols are UEFI interfaces
- Supports complex bus hierarchies
- Driver Binding Protocol matches drivers to devices & adds version management
- Supports specific hardware, can be unloaded or override an existing driver




+++?image=/assets/images/slides/Slide5.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Defining a UEFI Driver? 02]
<p align="right"><span class="gold" >Defining a UEFI Driver?</span></p>

Note:



+++?image=/assets/images/slides/Slide6.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Defining a UEFI Driver? 03]
<p align="right"><span class="gold" >Defining a UEFI Driver?</span></p>

Note:



+++?image=/assets/images/slides/Slide7.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Defining a UEFI Driver? 04]
<p align="right"><span class="gold" >Defining a UEFI Driver?</span></p>

Note:



+++?image=/assets/images/slides/Slide8.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Defining a UEFI Driver? 05]
<p align="right"><span class="gold" >Defining a UEFI Driver?</span></p>

Note:



---?image=/assets/images/slides/Slide10.JPG
@title[UEFI Drivers - Location]
<p align="right"><span class="gold" >UEFI Drivers - Location</span></p>

Note:

#### Boot flow diagram 
- UEFI Drivers depend on:
  -  the EFI system table
  -  Boot services
  -  runtime services 
  


---?image=/assets/images/slides/Slide12_1.JPG
@title[UEFI Drivers - Location II]
<p align="right"><span class="gold" >UEFI Drivers - Location</span></p>

Note:

- UEFI Drivers extend firmware … add support for new hardware with no operating system or platform dependence
- Portable across platforms … compile the same code across multiple architectures (IA32, x64, EFI Byte Code, Intel Itanium, …)


---?image=/assets/images/slides/Slide14.JPG
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>

Note:

Simlar to the Applications loading slide

+++?image=/assets/images/slides/Slide15.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 02]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide16.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 03]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide17.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 04]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide18.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 05]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide19.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 06]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide20.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 07]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide21.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 08]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


+++?image=/assets/images/slides/Slide22.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 09]
<p align="right"><span class="gold" >UEFI Drivers Vs. Applications</span></p>


Note:


---?image=/assets/images/slides/Slide25.JPG
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:

- What are the differences between a driver and an Application?

- Both have EFI_SYSTEM_TABLE and can then access the Handle Database

- UEFI drivers contains functions specific to one or more protocol implementations, and registers them with the InstallProtocolInterface() Boot Service 

- System firmware returns the Protocol Interface for the protocol that is then used to invoke the protocol specific service.


- The UEFI Driver keeps private, device specific context with the protocol interfaces.
  - Examples:
  - Device Path, PCI I/O, Disk I/O, GOP, UNDI

   -  See § 2.4 UEFI 2.x Spec.





+++?image=/assets/images/slides/Slide26.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 02]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide27.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 03]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide28.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 04]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide29.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 05]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide30.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 06]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide31.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 07]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide32.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 08]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



+++?image=/assets/images/slides/Slide33.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 09]
<p align="right"><span class="gold" >Drivers Produce Protocols</span></p>


Note:



---?image=/assets/images/slides/Slide35.JPG
<!-- .slide: data-transition="none" -->
@title[UEFI Driver Binding Protocol]
<p align="center"><span class="gold" >UEFI Driver Binding Protocol</span></p>


Note:

- Supported ()
- Start()
- Stop()


+++?image=/assets/images/slides/Slide36.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Driver Binding Protocol 02]
<p align="center"><span class="gold" >UEFI Driver Binding Protocol</span></p>


Note:

Supported() - Checks if a driver supports a controller
Check should not change hardware state of controller 
Minimize execution time, move complex I/O to Start()
May be called for controller that is already managed
Child is optionally specified



+++?image=/assets/images/slides/Slide37.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Driver Binding Protocol 03]
<p align="center"><span class="gold" >UEFI Driver Binding Protocol</span></p>



Note:

Start() - Starts a driver on a controller
Can create ALL child handles or ONE child handle
A driver is not required to support starting ONE child handle.  It may always create ALL child handles.




+++?image=/assets/images/slides/Slide38.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Driver Binding Protocol 04]
<p align="center"><span class="gold" >UEFI Driver Binding Protocol</span></p>


Note:

Stop() - Stops a driver from managing a controller
Destroys all specified child handles 
If no children are specified, controller is stopped immediately
Stopping a bus controller requires two calls




---?image=/assets/images/slides/Slide40.JPG
@title[Supported - PCI Controller Device Handle]
<p align="right"><span class="gold" >Supported - PCI Controller Device Handle</span></p>

Note:


---?image=/assets/images/slides/Slide42.JPG
<!-- .slide: data-transition="none" -->
@title[Start - PCI Controller Device Handle]
<p align="right"><span class="gold" >Start - PCI Controller Device Handle</span></p>

Note:

+++?image=/assets/images/slides/Slide43.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Start - PCI Controller Device Handle 02]
<p align="right"><span class="gold" >Start - PCI Controller Device Handle</span></p>




---?image=/assets/images/slides/Slide45.JPG
<!-- .slide: data-transition="none" -->
@title[Start - PCI Controller Device Handle]
<p align="right"><span class="gold" >Stop - PCI Controller Device Handle</span></p>

Note:

+++?image=/assets/images/slides/Slide46.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stop - PCI Controller Device Handle 02]
<p align="right"><span class="gold" >Stop - PCI Controller Device Handle</span></p>


---?image=/assets/images/slides/Slide48.JPG
<!-- .slide: data-transition="none" -->
@title[Example:  UEFI Driver - ScsiDiskDxe]
<p align="right"><span class="gold" >Example:  UEFI Driver - ScsiDiskDxe</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Bus/Scsi/ScsiDiskDxe">edk2/MdeModulePkg/Bus/Scsi/ScsiDiskDxe</a></span><br>

Note:

+++?image=/assets/images/slides/Slide49.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Example:  UEFI Driver - ScsiDiskDxe 02 -1]
<p align="right"><span class="gold" >Example:  UEFI Driver - ScsiDiskDxe</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Bus/Scsi/ScsiDiskDxe">edk2/MdeModulePkg/Bus/Scsi/ScsiDiskDxe</a></span><br>

Note:

- Entry point, Global Protocols – see the BY_START and TO_START usages in the protocols

+++
@title[Example:  UEFI Driver - ScsiDiskDxe 02 -2]
<p align="right"><span class="gold" >Example:  UEFI Driver - ScsiDiskDxe</span></p>
<br>
```php
[Defines]
  INF_VERSION                    = 0x00010005
  BASE_NAME                      = ScsiDisk
  MODULE_UNI_FILE                = ScsiDisk.uni
  FILE_GUID                      = 0A66E322-3740-4cce-AD62-BD172CECCA35
  MODULE_TYPE                    = UEFI_DRIVER
  VERSION_STRING                 = 1.0

  ENTRY_POINT                    = InitializeScsiDisk

[Sources]
  ComponentName.c
  ScsiDisk.c
  ScsiDisk.h

[Packages]
  MdePkg/MdePkg.dec


[LibraryClasses]
  UefiBootServicesTableLib
  UefiScsiLib
  BaseMemoryLib
  MemoryAllocationLib
  UefiLib
  UefiDriverEntryPoint
  DebugLib
  DevicePathLib

[Protocols]
  gEfiDiskInfoProtocolGuid                      ## BY_START
  gEfiBlockIoProtocolGuid                       ## BY_START
  gEfiBlockIo2ProtocolGuid                      ## BY_START
  gEfiEraseBlockProtocolGuid                    ## BY_START
  gEfiScsiIoProtocolGuid                        ## TO_START
  gEfiScsiPassThruProtocolGuid                  ## TO_START
  gEfiExtScsiPassThruProtocolGuid               ## TO_START

[Guids]
  gEfiDiskInfoScsiInterfaceGuid                 ## SOMETIMES_PRODUCES ## UNDEFINED
  gEfiDiskInfoIdeInterfaceGuid                  ## SOMETIMES_PRODUCES ## UNDEFINED
  gEfiDiskInfoAhciInterfaceGuid                 ## SOMETIMES_PRODUCES ## UNDEFINED
  gEfiDiskInfoUfsInterfaceGuid                  ## SOMETIMES_PRODUCES ## UNDEFINED

# [Event]
# EVENT_TYPE_RELATIVE_TIMER       ## CONSUMES
#

[UserExtensions.TianoCore."ExtraFiles"]
  ScsiDiskExtra.uni

```

Note:


---?image=/assets/images/slides/Slide50.JPG
@title[Example:  UEFI Driver - ScsiDiskDxe 03 -1]
<p align="right"><span class="gold" >Example:  UEFI Driver - ScsiDiskDxe</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Bus/Scsi/ScsiDiskDxe">edk2/MdeModulePkg/Bus/Scsi/ScsiDiskDxe</a></span><br>

Note:

- Driver’s Private Data Structure declaration – Data structures for managing a SCSI disk device


+++?code=sample/ScsiDiskDxe/ScsiDisk.h&lang=c++&title=Example:  ScsiDisk.h



Note:



---?image=/assets/images/slides/Slide51.JPG
@title[Example:  UEFI Driver - ScsiDiskDxe 04 -1]
<p align="right"><span class="gold" >Example:  UEFI Driver - ScsiDiskDxe</span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Bus/Scsi/ScsiDiskDxe">edk2/MdeModulePkg/Bus/Scsi/ScsiDiskDxe</a></span><br>

Note:

- Driver’s Private Data Structure declaration – Data structures for managing a SCSI disk device


+++?code=sample/ScsiDiskDxe/ScsiDisk.c&lang=c++&title=Example:  ScsiDisk.c

Note:



---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Driver Wizard ]
<br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Wizard</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Creating a Template UEFI Driver with the </span><br>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Wizard</span>

---?image=/assets/images/slides/Slide54.JPG
@title[UEFI Driver Wizard  Overview]
<br>
<p align="left"><span class="gold" >UEFI Driver Wizard  Overview</span></p>
<br>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><font color="cyan">&check;&nbsp;&nbsp;Open source tool  </font> </span>  </li>
  <li><span style="font-size:0.8em" ><font color="white">&check;&nbsp;&nbsp;Based on Driver Writer’s Guide for UEFI 2.3.1 content</font> </span>  </li>
  <li><span style="font-size:0.8em" ><font color="cyan">&check;&nbsp;&nbsp;Intel engineers contributed   </font> </span>  </li>
  <li><span style="font-size:0.8em" ><font color="white">&check;&nbsp;&nbsp;Located on <a href="http://www.tianocore.org">www.TianoCore.org</a>  </font> </span>  </li>
</ul>
</div>
<div class="right1">
  <span style="font-size:0.8em" > &nbsp;&nbsp;</span> 
</div>

Note:

---?image=/assets/images/slides/Slide56.JPG
@title[Installing Python for UEFI Driver Wizard]
<p align="right"><span class="gold" >Installing Python for UEFI Driver Wizard</span></p>
<span style="font-size:01.0em" ><font color="#92D050">Requirements and Options </font></span><br>
<br>
<ul style="list-style-type:disc">
  <li><span style="font-size:0.8em" >Work space  must contain BaseTools, MdePkg & MdeModulePkg Packages from <a href="https://github.com/tianocore/tianocore.github.io/wiki/Driver-Developer">UDK2018</a> for Driver development on Tianocore.org </span> </li>
  <li><span style="font-size:0.8em" >Uses previous lab’s setup `$HOME/src/edk2`   </span> </li>
  <li><span style="font-size:0.8em" >Python scripts from  <a href="https://github.com/tianocore/edk2-share/tree/master/DriverDeveloper/UefiDriverWizard">Github Link </a> then use instructions from README for Python and wxPython versions to install then run</span> </li>
  <ul style="list-style-type:none">
    <li><span style="font-size:0.6em" >&nbsp;&nbsp;<span style="background-color: #101010">`bash$ python launch.py`</span> </span></li>
  </ul>
</ul>

Note:

Same as slide


---?image=/assets/images/slides/Slide58.JPG
@title[Requirements for Your Driver ]
<br>
<p align="center"><span class="gold" >Requirements for Your Driver </span></p>
<span style="font-size:0.9em" >Using UEFI Driver Wizard</span>
<ul>
   <li><span style="font-size:0.7em" >UEFI Device Driver </span></li>
   <li><span style="font-size:0.7em" >UEFI Version 2.7 (0x00020046) </span><br><span style="font-size:0.6em" >`#define EFI_2_70_SYSTEM_TABLE_REVISION ((2<<16) | (70DEC))` </span></li>
   <li><span style="font-size:0.7em" >Unloadable driver </span></li>
   <li><span style="font-size:0.7em" >Support IA32 & x64 CPUs </span></li>
   <li><span style="font-size:0.7em" >Returns component name information </span></li>
   <li><span style="font-size:0.7em" >Test console device </span></li>
   <li><span style="font-size:0.7em" >Option to produce strings & forms for setup  </span></li>
</ul>

Note:


---?image=/assets/images/slides/Slide60.JPG
<!-- .slide: data-transition="none" -->
@title[Template File Contents]
<p align="right"><span class="gold" >Template File Contents </span></p>

Note:
- Establishes a proper UEFI Driver Entry Point
- References to basic driver libraries/headers based on Driver Wizard form input
- Inserted in .INF, .H and .C files
- Skeletons for common driver functions
- Includes comments based on information from the Driver Writer’s Guide for UEFI 2.3.1
- Functions may return error values until ported : (EFI_UNSUPPORTED, EFI_DEVICE_ERROR)



+++?image=/assets/images/slides/Slide61.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Template File Contents 02]
<p align="right"><span class="gold" >Template File Contents </span></p>

Note:
- Establishes a proper UEFI Driver Entry Point
- References to basic driver libraries/headers based on Driver Wizard form input
- Inserted in .INF, .H and .C files
- Skeletons for common driver functions
- Includes comments based on information from the Driver Writer’s Guide for UEFI 2.3.1
- Functions may return error values until ported : (EFI_UNSUPPORTED, EFI_DEVICE_ERROR)


+++?image=/assets/images/slides/Slide62.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Template File Contents 03]
<p align="right"><span class="gold" >Template File Contents </span></p>

Note:
- Establishes a proper UEFI Driver Entry Point
- References to basic driver libraries/headers based on Driver Wizard form input
- Inserted in .INF, .H and .C files
- Skeletons for common driver functions
- Includes comments based on information from the Driver Writer’s Guide for UEFI 2.3.1
- Functions may return error values until ported : (EFI_UNSUPPORTED, EFI_DEVICE_ERROR)


+++?image=/assets/images/slides/Slide63.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Template File Contents 04]
<p align="right"><span class="gold" >Template File Contents </span></p>

Note:
- Establishes a proper UEFI Driver Entry Point
- References to basic driver libraries/headers based on Driver Wizard form input
- Inserted in .INF, .H and .C files
- Skeletons for common driver functions
- Includes comments based on information from the Driver Writer’s Guide for UEFI 2.3.1
- Functions may return error values until ported : (EFI_UNSUPPORTED, EFI_DEVICE_ERROR)

---
@title[Lab 1: Install UEFI Driver Wizard, Python & wxPython ]
<br>
<p align="right"><span class="gold" >Lab 1: Install UEFI Driver Wizard, Python & wxPython</span></p>
<ol>
   <li><span style="font-size:0.8em" >Perform <a href="https://gitpitch.com/Laurie0131/Platform_Build_LAB/master#/">Lab Setup</a> from previous Labs  </span></li>
   <li><span style="font-size:0.8em" >From the `~FW/DriverWizard` folder, copy and paste folder “`~FW/DriverWizard/UefiDriverWizard`” to `~$Home`  </span></li>
   <li><span style="font-size:0.8em" >Check  if version 2.7.x is the default of Python from Terminal Prompt </span></li>
   <ul style="list-style-type:none">
       <li><span style="font-size:0.6em" ><span style="background-color: #101010">`bash$ python –V`&nbsp;&nbsp;</span></span></li>
       <li><span style="font-size:0.6em" ><span style="background-color: #300a24">`Python 2.7.12`&nbsp;&nbsp;&nbsp;&nbsp;</span></span></li>
   </ul>
   <li><span style="font-size:0.8em" >Install the wxPython  (Version 3.0 ) </span></li>
   <ul style="list-style-type:none">
       <li><span style="font-size:0.6em" ><span style="background-color: #101010">`bash$ sudo apt-get install python-wxgtk3.0` &nbsp;&nbsp;</span></span></li>
   </ul>
</ol>

Note:

same as slide


---?image=/assets/images/slides/Slide67.JPG
@title[Lab 1: UefiDriverWizard -Select Work Space]
<p align="right"><span class="gold" >Lab 1: UefiDriverWizard -Select Work Space</span></p>

Note:
- Terminal Prompt (Cnt-Alt-T)
  - `bash$ cd ~UefiDriverWizard`
  - `bash$ python launch.py`

- Select a Work Space
- Control+O – to  browse for a directory

- Browse to ~src/edk2 

- Select Open



---?image=/assets/images/slides/Slide69.JPG
@title[Lab 1: -Create a New UEFI Driver]
<p align="center"><span class="gold" >Lab 1: Create a <u>N</u>ew UEFI Driver</span></p>

Note:
- Control+N – to Open Menu 


---?image=/assets/images/slides/Slide71.JPG
@title[Lab 1: New UEFI Driver Menu]
<p align="left"><span class="gold" >&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp;Lab 1:</span></p>
<p align="left"><span class="gold" >New UEFI Driver Menu</span></p>
<div class="left1">
<ul style="list-style-type:disc">
  <li><span style="font-size:0.7em" >“UEFI Driver Path” – Type: <b>“MyWizardDriver”</b></span>  </li>
    <ul style="list-style-type:none">
     <li><span style="font-size:0.5em" >&nbsp;&nbsp;<i>Note:</i> “UEFI Driver Name” is filled in </span>  </li>
  </ul>
 <li><span style="font-size:0.7em" ><b>Ensure</b> all the forms, radio buttons, and boxes are filled in and <b>selected exactly</b> like the image to the right.</span>  </li>
 <br>
 <li><span style="font-size:0.65em" ><i>Note:</i>A new, specific driver GUID will populate, so it will be different than this image</span>  </li>
   <br>
  <ul style="list-style-type:none">
       <li><span style="font-size:0.8em" >&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
  </ul>
</ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:
- “UEFI Driver Version” – Type: “1.0”
- “UEFI Driver Type” – Select: “UEFI Driver Model Device Driver”
- “Opetional Features …” – Select:
  - 	Unloadable
  - 	Driver Supporte EFI Version Protocol
  - 	HII Packages for Strings, Fonts, or images
- “CPU Architecture” – Select: “IA32” and “X64”





---?image=/assets/images/slides/Slide73.JPG
@title[Lab 1: UEFI Driver Model Optional Features]
<br>
<p align="left"><span class="gold" >Lab 1: UEFI Driver Model Optional Features</span></p>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><b>Ensure</b> all the forms, radio buttons, and boxes are filled in and <b>selected exactly</b> like the image to the right.</span>  </li>
  <br>
  <br>
  <li><span style="font-size:0.6em" >&check;&nbsp;&nbsp;"Componnt Name 2 Prorocol”  </span>  </li>
  <li><span style="font-size:0.6em" >&check;&nbsp;&nbsp;"Componnt Name Prorocol”   </span>  </li>
  <li><span style="font-size:0.6em" >&check;&nbsp;&nbsp;"HII Packages for Forms . . .”  </span>  </li>
  <br>
  <br>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
 </ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:

- UEFI Driver Model Opetional Features  – Select:
  -	Componnt Name 2 Prorocol
  -	Componnt Name 2 Prorocol
  -	HII Packages for Forms and HII based configuruation





---?image=/assets/images/slides/Slide75.JPG
@title[Lab 1: UEFI Driver Consumed Protocol]
<br>
<p align="left"><span class="gold" >Lab 1: UEFI Driver Consumed Protocol</span></p>
<span style="font-size:0.8em" ><b>Select</b></span> <br>
<span style="font-size:0.7em" >&check;&nbsp;&nbsp;"PCI Driver that consumes the PCI I/O Protocol”  </span>  
<div class="left1">
<ul style="list-style-type:none">
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp; &nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
</ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:

Same as slide





---?image=/assets/images/slides/Slide77_1.JPG
@title[Lab 1: UEFI Driver Produced Protocols]
<p align="right"><span class="gold" >Lab 1: UEFI Driver Produced Protocols</span></p>
<br>
<div class="left1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" ><b>Select</b></span>  </li>
  <li><span style="font-size:0.7em" >&check;&nbsp;&nbsp;"Byte stream device (i.e.UART) &nbsp; <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; producing Serial I/O Protocol”  </span>  </li>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <br>
  <li><span style="font-size:0.8em" >&nbsp;&nbsp; &nbsp; &nbsp;&nbsp;&nbsp; &nbsp; &nbsp; <b>Click</b>  </li>
</ul>
</div>
<div class="right1">
<ul style="list-style-type:none">
  <li><span style="font-size:0.8em" >&nbsp;  </li>
</ul>
</div>

Note:

Same as slide



---?image=/assets/images/slides/Slide79_1.JPG
@title[Lab 1: UEFI Driver Created]
<br>
<p align="left"><span class="gold" >Lab 1: UEFI Driver Created</span></p>
<span style="font-size:0.8em" > UEFI Driver template created</span>

Note:

Same as slide

---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;What is the UEFI Driver Model</span> </li><br>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Setup the UEFI Driver Wizard</span></li><br>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Create a UEFI Driver Template</span> </li>
</ul>


 

---?image=assets/images/gitpitch-audience.jpg
@title[Questions]
<br>
![Questions](/assets/images/questions.JPG) 


---?image=assets/images/gitpitch-audience.jpg
@title[Logo Slide]
<br><br><br>
![Logo Slide](/assets/images/TianocoreLogo.png =10x)


---
@title[Acknowledgements]
#### <p align="center"><span class="gold"   >Acknowledgements</span></p>

```c++
/**
Redistribution and use in source (original document form) and 'compiled' forms (converted
to PDF, epub, HTML and other formats) with or without modification, are permitted provided
that the following conditions are met:

Redistributions of source code (original document form) must retain the above copyright 
notice, this list of conditions and the following disclaimer as the first lines of this 
file unmodified.

Redistributions in compiled form (transformed to other DTDs, converted to PDF, epub, HTML
and other formats) must reproduce the above copyright notice, this list of conditions and 
the following disclaimer in the documentation and/or other materials provided with the 
distribution.

THIS DOCUMENTATION IS PROVIDED BY TIANOCORE PROJECT "AS IS" AND ANY EXPRESS OR IMPLIED 
WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND 
FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL TIANOCORE PROJECT BE 
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES 
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, 
WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) 
ARISING IN ANY WAY OUT OF THE USE OF THIS DOCUMENTATION, EVEN IF ADVISED OF THE POSSIBILITY 
OF SUCH DAMAGE.

Copyright (c) 2018, Intel Corporation. All rights reserved.
**/

```
