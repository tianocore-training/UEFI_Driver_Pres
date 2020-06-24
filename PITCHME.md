---?image=assets/images/gitpitch-audience.jpg
@title[UEFI_Driver_Pres]
<br><br><br><br><br>
## <span class="gold"   >UEFI & EDK II Training</span>

#### How to Write a UEFI Driver

<br>
<span style="font-size:0.75em" ><a href='http://www.tianocore.org'>tianocore.org</a></span>
Note:
  PITCHME.md for UEFI / EDK II Training  UEFI Driver Model and Driver Wizard Pres

  Copyright (c) 2020, Intel Corporation. All rights reserved.<BR>

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
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Details on Driver Binding Protocol</span></li><br>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Example of UEFI Driver</span> </li>
</ul>

---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Driver Model]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Model </span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span>


---?image=/assets/images/slides/Slide10.JPG
@title[UEFI Drivers - Location]
<p align="right"><span class="gold" ><b>UEFI Drivers - Location</b></span></p>

Note:

#### Boot flow diagram 
- UEFI Drivers depend on:
  -  the EFI system table
  -  Boot services
  -  runtime services 
  

---?image=/assets/images/slides/Slide5_1.JPG
@title[What are UEFI Drivers ?]
<p align="left"><span class="gold" ><br>@size[1.1em](<b>What are UEFI Drivers ? </b>)</span><br>
<span style="font-size:0.75em;" >  </span></p>

@snap[south-east span-15 fragment ]
<p style="line-height:40%" align="left" ><span style="font-size:0.57em;" >New UEFI Driver</span></p>
![Newblock](/assets/images/newBlock.png) 
<br>
<br>
<br>
<br>
@snapend




@snap[north-west span-60 fragment ]
<br>
<br>
<br>
<br>
<br>
<ul style="list-style-type:disc; line-height:0.9;">
  <li><span style="font-size:0.87em;" >UEFI Drivers extend firmware  </span>   </li>
  <li><span style="font-size:0.87em;" >Portable across platforms   </span>   </li>
  <li><span style="font-size:0.87em;" >Enables rapid development  </span>   </li>
  <li><span style="font-size:0.87em;" >Produce Protocols  </span>   </li>
</ul>
@snapend


@snap[south-west span-70 fragment]
<br>
<br>
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%" align="center" ><span style="font-size:0.85em; font-weight: bold;" > UEFI driver is chained into a link lst of<br>@color[yellow](Drivers Managing Devices) <br>&nbsp;</span></p>)
<br>
@snapend


Note:
So what do UEFI Drivers do?
  More than anything UEFI drivers extend the firmware. 
  They add support for new hardware without any Hardware or OS dependence. – 
  What that means is --   The UEFI driver does not need a specific piece of hardware, a UEFI Driver will allow new hardware to exist and will manage this new hardware but does not depend on any other hardware or OS manager. In other words, a UEFI driver is chained into a link list of drivers and devices
Drivers can be Portable across platform architectures
IA32, X64 
Enables rapid development – Enable reuse and through the driver protocols enable rapid development

UEFI and PI Drivers produce protocols. – that can be used by anything else in the UEFI System


  





---
@title[Defining a UEFI Driver?]
<p align="right"><span class="gold" ><b>Defining a UEFI Driver?</b></span></p>

@snap[north-west span-60 fragment]
<br>
<br>
@box[bg-purple-pp text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" > UEFI Loadable Image <br>&nbsp;</span></p>)
<br>
@snapend


@snap[north-east span-65 fragment]
<br>
<br>
<p style="line-height:50%" ><br><br>&nbsp;</p>
@box[bg-gold2 text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" >May produce/consume protocols<br>&nbsp;</span></p>)
<br>
@snapend


@snap[north-west span-70 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
@box[bg-royal text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" > Supports complex bus hierarchies<br>&nbsp;</span></p>)
<br>
@snapend



@snap[north-east span-90 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" ><br>&nbsp;<br>&nbsp;</p>
@box[bg-navy text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" >Driver Binding Protocol matches drivers to devices, adds version management<br>&nbsp;</span></p>)
<br>
@snapend



@snap[north-west span-100 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:50%" ><br>&nbsp;</p>
@box[bg-green2 text-white rounded my-box-pad2  ](<p style="line-height:70%" ><span style="font-size:0.9em; font-weight: bold;" > Supports specific hardware, can be unloaded or override an existing driver<br>&nbsp;</span></p>)
<br>
@snapend







Note:

- An UEFI Loadable Image
- May produce or consume protocols
- Protocols are UEFI interfaces
- Supports complex bus hierarchies
- Driver Binding Protocol matches drivers to devices & adds version management
- Supports specific hardware, can be unloaded or override an existing driver





---?image=/assets/images/slides/Slide12_1.JPG
@title[UEFI Drivers - Location II]
<p align="right"><span class="gold" ><b>UEFI Drivers - Location</b></span></p>

Note:

- UEFI Drivers extend firmware … add support for new hardware with no operating system or platform dependence
- Portable across platforms … compile the same code across multiple architectures (IA32, x64, EFI Byte Code, Intel Itanium, …)


---?image=/assets/images/slides/Slide14.JPG
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>

Note:

Simlar to the Applications loading slide

+++?image=/assets/images/slides/Slide15.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 02]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide16.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 03]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide17.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 04]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide18.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 05]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide19.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 06]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide20.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 07]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide21.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 08]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


+++?image=/assets/images/slides/Slide22.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[UEFI Drivers Vs. Applications 09]
<p align="right"><span class="gold" ><b>UEFI Drivers Vs. Applications</b></span></p>


Note:


---?image=/assets/images/slides/Slide25.JPG
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


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
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide27.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 03]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide28.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 04]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide29.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 05]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide30.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 06]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide31.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 07]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide32.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 08]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:



+++?image=/assets/images/slides/Slide33.JPG
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Drivers Produce Protocols 09]
<p align="right"><span class="gold" ><b>Drivers Produce Protocols</b></span></p>


Note:






---
@title[UEFI Driver Binding Protocol]
<p align="center"><span class="gold" ><b>UEFI Driver Binding Protocol</b></span></p>



@snap[north-west span-20 fragment]
<br>
<br>
<p style="line-height:40%" align="left"><span style="font-size:02.250em;" >@fa[star  gp-bullet-cyan] </span></p>
@snapend

@snap[north-east span-85 fragment]
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:01.25em; font-family:Consolas;" >@color[yellow](Supported&lpar;&rpar;) </span> <span style="font-size:0.85em;" ><br> 
Determines if a driver supports a controller </span></p>
@snapend



@snap[north-west span-20 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:40%" align="left"><span style="font-size:02.250em;" >@fa[star  gp-bullet-ltgreen] </span></p>
@snapend

@snap[north-east span-85 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:01.25em; font-family:Consolas;" >@color[yellow](Start&lpar;&rpar;) </span> <span style="font-size:0.85em;" ><br> 
Starts a driver on a controller &amp; Installs Protocols </span></p>
@snapend



@snap[north-west span-20 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:40%" align="left"><span style="font-size:02.250em;" >@fa[star  gp-bullet-gold] </span></p>
@snapend

@snap[north-east span-85 fragment]
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:01.25em; font-family:Consolas;" >@color[yellow](Stop&lpar;&rpar;) </span> <span style="font-size:0.85em;" ><br> 
Stops a driver from managing a controller </span></p>
@snapend

Note:

- Supported ()
- Start()
- Stop()

Supported() - Checks if a driver supports a controller Check should not change hardware state of controller 
Minimize execution time, move complex I/O to Start() May be called for controller that is already managed Child is optionally specified

Start() - Starts a driver on a controller
Can create ALL child handles or ONE child handle
A driver is not required to support starting ONE child handle.  It may always create ALL child handles.

Stop() - Stops a driver from managing a controller
Destroys all specified child handles 
If no children are specified, controller is stopped immediately
Stopping a bus controller requires two calls



---
@title[Supported - PCI Controller Device Handle]
<p align="right"><span class="gold" ><b>Supported - PCI Controller Device Handle</b></span></p>
@snap[north-west span-50]
<br>
<br>
<table id="recTable-90">
	<tr>
       <td bgcolor="#121212" height=".025" align="center"><p style="line-height:010%"><span style="font-size:0.65em" ><b>PCI Controller Device Handle</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_DEVICE_PATH_PROTOCOL`</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_PCI_IO_PROTOCOL`</span></p></td>
	</tr>
</table>

@snapend

@snap[west span-50 fragment]
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="cyan">Tasks:</font></span></p>
<ul style="list-style-type:none; line-height:0.7;">
	<li><span style="font-size:0.7em" >1. @color[yellow](Opens) PCI_IO Protocol</span></li>
	<li><span style="font-size:0.7em" >2. Checks</span></li>
	<li><span style="font-size:0.7em" >3. @color[yellow](Closes) PCI_IO Protocol</span></li>
	<li><span style="font-size:0.7em" >4. Returns: Supported or Not<br>&nbsp;&nbsp;&nbsp;&nbsp;Supported</span></li>
</ul>
@snapend



@snap[north-east span-50 fragment]
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="cyan">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Inputs:</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.7em" > “This”  </span></li>
  <li><span style="font-size:0.7em" >  Controller to manage</span></li>
  <li><span style="font-size:0.7em" >  Remaining Device Path&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span></li>
</ul>
@snapend

@snap[east span-50 fragment]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="yellow">`Supported()`</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
   <li><span style="font-size:0.7em" > Checks to see if a driver supports a controller </span></li>
   <li><span style="font-size:0.7em" > Check should not change hardware state of controller  </span></li>
   <li><span style="font-size:0.7em" > Minimize execution time, move complex I/O to Start() </span></li>
   <li><span style="font-size:0.7em" > May be called for controller that is  already managed </span></li>
   <li><span style="font-size:0.7em" > Child is optionally specified </span></li>
</ul>

@snapend

Note:

---
@title[Start - PCI Controller Device Handle]
<p align="right"><span class="gold" ><b>Start - PCI Controller Device Handle</b></span></p>






@snap[north-east span-50 fragment]
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="cyan">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Inputs:</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.7em" > “This”  </span></li>
  <li><span style="font-size:0.7em" >  Controller to manage</span></li>
  <li><span style="font-size:0.7em" >  Remaining Device Path&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span></li>
</ul>
@snapend

@snap[east span-50 fragment]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="yellow">`Start()`</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
   <li><span style="font-size:0.7em" > @color[yellow](Opens) PCI I/O Protocol </span></li>
   <li><span style="font-size:0.7em" > Starts a driver on a controller</span></li>
   <li><span style="font-size:0.7em" > Can create ALL child handles or ONE child handle (i.e. Call Install Library)</span></li>
</ul>

@snapend

@snap[north-west span-50]
<br>
<br>
<table id="recTable-90">
	<tr>
       <td bgcolor="#121212" height=".025" align="center"><p style="line-height:010%"><span style="font-size:0.65em" ><b>PCI Controller Device Handle</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_DEVICE_PATH_PROTOCOL`</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_PCI_IO_PROTOCOL`</span></p></td>
	</tr>
	<tr class="fragment">
		<td  bgcolor="#7f7f7f" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_BLOCK_IO_PROTOCOL`</span></p></td>
	</tr>
</table>

@snapend


Note:



---
<!-- .slide: data-transition="none" -->
@title[Stop - PCI Controller Device Handle]
<p align="right"><span class="gold" ><b>Stop - PCI Controller Device Handle</b></span></p>

@snap[north-west span-50]
<br>
<br>
<table id="recTable-90">
	<tr>
       <td bgcolor="#121212" height=".025" align="center"><p style="line-height:010%"><span style="font-size:0.65em" ><b>PCI Controller Device Handle</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_DEVICE_PATH_PROTOCOL`</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_PCI_IO_PROTOCOL`</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#7f7f7f" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_BLOCK_IO_PROTOCOL`</span></p></td>
	</tr>
</table>

@snapend

@snap[north-east span-50 fragment]
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="cyan">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Inputs:</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.7em" > “This”  </span></li>
  <li><span style="font-size:0.7em" >  Controller to manage</span></li>
  <li><span style="font-size:0.7em" >  Remaining Device Path&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span></li>
</ul>
@snapend



@snap[east span-50 fragment]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="yellow">`Stop()`</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
   <li><span style="font-size:0.7em" > @color[yellow](Closes) PCI I/O Protocol </span></li>
   <li><span style="font-size:0.7em" > Destroys all specified child handles (i.e. Call Uninstall)  </span></li>
   <li><span style="font-size:0.7em" > If no children specified, controller is stopped </span></li>
   <li><span style="font-size:0.7em" > Stopping a bus controller requires 2 calls </span></li>
   <ul style="list-style-type:none; line-height:0.7;">
		<li><span style="font-size:0.7em" > One call to stop the children.  A second call to stop the bus controller itself </span></li>
   </ul>
</ul>

@snapend



Note:


+++
<!-- .slide: data-background-transition="none" -->
<!-- .slide: data-transition="none" -->
@title[Stop - PCI Controller Device Handle 02]
<p align="right"><span class="gold" ><b>Stop - PCI Controller Device Handle</b></span></p>

@snap[north-west span-50]
<br>
<br>
<table id="recTable-90">
	<tr>
       <td bgcolor="#121212" height=".025" align="center"><p style="line-height:010%"><span style="font-size:0.65em" ><b>PCI Controller Device Handle</b></span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_DEVICE_PATH_PROTOCOL`</span></p></td>
	</tr>
	<tr>
		<td  bgcolor="#404040" height=".02"><p style="line-height:010%"><span style="font-size:0.45em" >`EFI_PCI_IO_PROTOCOL`</span></p></td>
	</tr>
</table>

@snapend


@snap[north-east span-50 ]
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="cyan">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Inputs:</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
  <li><span style="font-size:0.7em" > “This”  </span></li>
  <li><span style="font-size:0.7em" >  Controller to manage</span></li>
  <li><span style="font-size:0.7em" >  Remaining Device Path&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</span></li>
</ul>
@snapend



@snap[east span-50 ]
<br>
<br>
<br>
<br>
<br>
<p style="line-height:85%" align="left"><span style="font-size:0.9em" ><font color="yellow">`Stop()`</font></span></p>
<ul style="list-style-type:disc; line-height:0.7;">
   <li><span style="font-size:0.7em" > @color[yellow](Closes) PCI I/O Protocol </span></li>
   <li><span style="font-size:0.7em" > Destroys all specified child handles (i.e. Call Uninstall)  </span></li>
   <li><span style="font-size:0.7em" > If no children specified, controller is stopped </span></li>
   <li><span style="font-size:0.7em" > Stopping a bus controller requires 2 calls </span></li>
   <ul style="list-style-type:none; line-height:0.7;">
		<li><span style="font-size:0.7em" > One call to stop the children.  A second call to stop the bus controller itself </span></li>
   </ul>
</ul>
 
@snapend



Note:


---?image=assets/images/binary-strings-black2.jpg
@title[UEFI Driver Example Section ]
<br><br><br><br><br><br><br>
### <span class="gold"  >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UEFI Driver Example</span>
<span style="font-size:0.9em" >&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Exam details of the UEFI Driver - ScsiDiskDxe </span><br>



---?image=/assets/images/slides/Slide48.JPG
<!-- .slide: data-transition="none" -->
@title[Example:  UEFI Driver - ScsiDiskDxe]
<p align="right"><span class="gold" ><b>Example:  UEFI Driver - ScsiDiskDxe</b></span></p>
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
<p align="right"><span class="gold" ><b>Example:  UEFI Driver - ScsiDiskDxe</b></span></p>
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

@[8-9](Entry point function)

Note:


---?image=/assets/images/slides/Slide50.JPG
@title[Example:  UEFI Driver - ScsiDiskDxe 03 -1]
<p align="right"><span class="gold" ><b>Example:  UEFI Driver - ScsiDiskDxe</b></span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Bus/Scsi/ScsiDiskDxe">edk2/MdeModulePkg/Bus/Scsi/ScsiDiskDxe</a></span><br>

Note:

- Driver’s Private Data Structure declaration – Data structures for managing a SCSI disk device


+++?code=sample/ScsiDiskDxe/ScsiDisk.h&lang=c++&title=Example:  ScsiDisk.h

@[55-99]( UEFI Driver's Private Data Structure declaration)

Note:



---?image=/assets/images/slides/Slide51.JPG
@title[Example:  UEFI Driver - ScsiDiskDxe 04 -1]
<p align="right"><span class="gold" ><b>Example:  UEFI Driver - ScsiDiskDxe</b></span></p>
<br>
@fa[github gp-bullet-black]<span style="font-size:0.7em">&nbsp;&nbsp;<a href="https://github.com/tianocore/edk2/tree/master/MdeModulePkg/Bus/Scsi/ScsiDiskDxe">edk2/MdeModulePkg/Bus/Scsi/ScsiDiskDxe</a></span><br>

Note:

- Driver’s Private Data Structure declaration – Data structures for managing a SCSI disk device


+++?code=sample/ScsiDiskDxe/ScsiDisk.c&lang=c++&title=Example:  ScsiDisk.c

@[16-33](Module Data Structures for Binding Protocol and SCSI Dick Info Protocol - Produced)
@[89-113]( Entry point, notice only Install of Binding and Component Name Protocol)
@[134-174]( The Supported Function, Only Checks and returns Supported or Unsupported)
@[196-204](Start Function Entry)
@[318-337](Start calls Install function to create handles for Multiple Protocols)
@[394-402](Stop Function Entry)
@[439-459](Stop Calls Un-install function matching the Start's Install)


Note:

- See the Start makes a call : Status = gBS->InstallMultipleProtocolInterfaces Line 320




---  
@title[Summary]
<BR>
### <p align="center"><span class="gold"   >Summary </span></p><br>
<ul style="list-style-type:none">
 <li>@fa[certificate gp-bullet-green]<span style="font-size:0.9em">&nbsp;&nbsp;What is the UEFI Driver Model</span> </li><br>
 <li>@fa[certificate gp-bullet-cyan]<span style="font-size:0.9em">&nbsp;&nbsp;Details on Driver Binding Protocol</span></li><br>
 <li>@fa[certificate gp-bullet-yellow]<span style="font-size:0.9em">&nbsp;&nbsp;Example of UEFI Driver</span> </li>
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

Copyright (c) 2020, Intel Corporation. All rights reserved.
**/

```
