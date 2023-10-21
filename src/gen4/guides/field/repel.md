# Tutorial Name
> This guide was written by SpagoAsparago. Credits to BluRose for helping with the assembly.

This is a tutorial on how to implement a reusable repel in Plat and HGSS, either with a multi-choice menu when a repels runs out:

Or the BW2 system, where the prompt triggers only if you have another of the same type of repel that just run out.

**Only works with US versions of those games**

--- 
## Table of Contents
* [Scripting](#section-1)
  * [Multi-Choice](#subsection)
  * [BW2 Sytem](#subsection-1)
* [Text](#section-2)
* [Custom Command](#section-3)

## Scripting

In DSPRE, go to the Script Editor and open script file [number], then change the following Scripts and Functions:

### Multi-choice

<details>
 <summary>Platinum</summary>
 <p>Replace Script 33 with the following Script:

```
Script 33:
	PlayFanfare 1500
	LockAll 
    	CheckPlayerHasItem 79 1 0x800C
	CompareVarValue 0x800C 1
	JumpIf EQUAL Function#177
	CheckPlayerHasItem 76 1 0x800C
	CompareVarValue 0x800C 1
	JumpIf EQUAL Function#177
	CheckPlayerHasItem 77 1 0x800C
	CompareVarValue 0x800C 1
	JumpIf EQUAL Function#177
	Message 79
	WaitAB 
	CloseMessage 
	ReleaseAll 
End
``` 
 
Then go to the function tab and add the following functions:

```
Function 177:
    Message 75
	YesNoBox 0x800C
	CompareVarValue 0x800C 0
	JumpIf EQUAL Function#178
	CloseMessage 
	ReleaseAll 
End
 
Function 178:
    	CloseMessage 
	MultiStandardText 1 1 0 1 0x800C
	CheckPlayerHasItem 79 1 0x8000
	CompareVarValue 0x8000 1
	CallIf EQUAL Function#179
	CheckPlayerHasItem 76 1 0x8000
	CompareVarValue 0x8000 1
	CallIf EQUAL Function#180
	CheckPlayerHasItem 77 1 0x8000
	CompareVarValue 0x8000 1
	CallIf EQUAL Function#181
	ShowMulti 
	CompareVarValue 0x800C 0
	JumpIf EQUAL Function#182
	CompareVarValue 0x800C 1
	JumpIf EQUAL Function#183
	CompareVarValue 0x800C 2
	JumpIf EQUAL Function#184
	ReleaseAll 
End
 
Function 179:
    AddMultiOption 30 0
Return
 
Function 180:
    AddMultiOption 31 1
Return
 
Function 181:
    AddMultiOption 32 2
Return
 
Function 182:
    AdrsValueSet 0x023DFF28 100
	DummyTakeTrap 
    TakeItem 79 1 0x8000
	TextPlayerName 0
	TextItem 1 79
	Message 72
	WaitButton 
	CloseMessage
Return
 
Function 183:
    AdrsValueSet 0x023DFF28 150
	DummyTakeTrap 
    TakeItem 76 1 0x8000
	TextPlayerName 0
	TextItem 1 76
	Message 72
	WaitButton 
	CloseMessage
Return
 
Function 184:
    AdrsValueSet 0x023DFF28 250
	DummyTakeTrap 
    TakeItem 77 1 0x8000
	TextPlayerName 0
	TextItem 1 77
	Message 72
	WaitButton 
	CloseMessage 
Return
```
 </p>
</details>


<details>
 <summary>HGSS</summary>
 <p>Hi, I am the details you asked for. You can hide me as well.</p>
</details>

### BW2 System

<details>
 <summary>Platinum</summary>
 <p>Hi, I am the details you asked for. You can hide me as well.</p>
</details>


<details>
 <summary>HGSS</summary>
 <p>Hi, I am the details you asked for. You can hide me as well.</p>
</details>

Remember to save the script file after you're done

## Text
In DSPRE text editor, open text file number and change the following lines:

<details>
 <summary>Platinum</summary>
 <p>Hi, I am the details you asked for. You can hide me as well.</p>
</details>


<details>
 <summary>HGSS</summary>
 <p>Hi, I am the details you asked for. You can hide me as well.</p>
</details>


## Custom Command
Since there is no way to access a dynamic address with regular scripting commands, a custom command is needed. I overwrote the unused command `DummyTakeTrap` (Pt) / `DummyTakeGoods` (HGSS).
For Platinum: if you haven't already, use DSPRE toolbox to perform the ARM9 expansion. The repel effect will write and read the byte at
`0x15FEE` in weather_sys_9.bin so remember to don't write anything at this offset.

Load the arm9 from your DSPRE's project folder (It's be named *YourROMName*_DSPRE_Content and is in the same folder as your ROM) in a hex editor, then paste the byte sequence listed below at the corresponding offset.
Do **not** add additional bytes, instead replace the existing bytes, in HxD you can use the `Ctrl+B` shortcut. For more information see the [Hex Editing guide for beginners](link)

<details>
 <summary>Platinum</summary>
<p>
Offset: `0x4EAE8`
  
Byte Sequence: ```0B 48 01 68 0B 48 09 18 0B 48 02 78 0A 70 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 C0 46 70 47 40 1D 10 02 87 80 00 00 28 FF 3D 02```
</p>
</details>


<details>
 <summary>HGSS</summary>
 <p>Hi, I am the details you asked for. You can hide me as well.</p>
</details>
