# Tasks.

**1. Load 2324FunDigiForensic Image**
**2. Make a simple text file and look at the data within using a Hex Editor** 
	1. Create a new text file on the desktop
	2. Open the file within HxD. ![[Pasted image 20231009101927.png]]
	3. Edit the text file then open the file again using HxD ![[Pasted image 20231009102141.png]]
**3. Number Systems Worksheet: Complete the following conversion grid.**

| Binary (unsigned) | Hexadecimal | Decimal |
|:----------------- |:----------- |:------- |
| 11101110          | EE          | 238     |
| 00011111          | 1F          | 31      |
| 00101001          | 29          | 41      |
| 10101010          | AA          | 170     |
| 101010111100      | ABC         | 2748    |
| 1111100           | 124         | 7C      |
| 0001010110100000  | 15A0        | 5536    |
| 10001100011101    | 231D        | 8989    |
| 10010                  | 12            |18         |

| Colour        | Hex Code R G B | Decimal Code R G B |
|:------------- |:-------------- |:------------------ |
| White         | FF FF FF       | 255 255 255        |
| Red           | FF 00 00       | 255 0 0            |
| Green         | 00 FF 00       | 0 255 0            |
| Blue          | 00 00 FF       | 0 0 255            |
| Yellow        | FF FF 00       | 255 255 0          |
| Pantone 448 C | 4A 41 2A       | 74 65 42           |

**4. Create an MD5 hash of each of the files in the HASH Values**

| File Name  | Hash Value                       |
|:---------- |:-------------------------------- |
| doc1       |e72cad83bf69757f936d13d2055bcd3a                                  |
| doc2.doc   | 99b8fb4f5836b07f974dd24530eb5f4d |
| doc3.txt   | 5825d7be8abd314dcb31602dc9abbdc3 |
| doc4.txt   | 34678e7fa7ca2f87cf3060e1ede54800 |
| doc5.doc   | f80917e6587a040639b8c7a97009c6e1                                 |
| doc6.doc   | 136903faf6ba51ae2361d9602d60a77d                                 |
| doc7.doc   | 07ce25b776e7b7cf0b60fa6ec215bbb3                                 |
| doc8.doc   |28804e786cd28a70a777ff66019859bf                                  |
| Image1.jpg |a2b132f425250972af1809819290b3ad                                  |
| image2.jpg | 4fd0247681673fcac997410b464eb9d0                                 |
| image3.jpg | ccf34e7e1770f956166ac89e5af366aa                                 |
| doc9.doc           | 07ce25b776e7b7cf0b60fa6ec215bbb3                                 |

**5. Create an MD5 hash of files to check if they change**
	1. Create Text Document `loan.txt`
		1. In the file write: `Tom owes Andrew £20.00`
		2. Save the file
		3. Calculate the MD5 Hash of the file
			1. `input here`
	2. Then make a copy called `copy of loan.txt` *Do not modify or OPEN this file*
		1. Compare the MD5 hash values
			- They are completely different because every different thing in a file will change the whole hash
	3. Open the loan.txt
		1. Change `Tom owes Andrew £20.00` to `Pip owes Andrew £2000`
		2. Save the file (override it)
		3. Calculate the hash and compare it to the others

**6. Make a software write blocker using the Windows Registry**
	1. Open regedit (Registry Editor)
	2. Navigate to `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet` and highlight the Control key. The CurrentControlSet key has system information about the current configuration of the machine
	3. Right Click on control and select `New > Key`, then name the key `StorageDevicePolicies`
	4. Right Click on `StorageDevicePolicies` then select `New > DWORD` then name the value `WriteProtect`
	5. Right Click on `WriteProtect` and select Modify. To write protect USB devices select 1 as the value. To turn off write protection, change this value to 0. 
	6. Select one to write-protect your USB thumb drive, then plug the USB thumb drive back into the top machine, and try to copy a picture file over to the thumb drive. You see a pop up (interrupted action) ![[Pasted image 20231009141739.png]]
		- We have created a new key, value on the reg that will protect USB devices. 
**7. Automate your software write blocker**
	1. Automate it by creating a .REG file to enable you to select either on or off
	2.  Right-click on `StorageDevicePolicies` and select `Export` (this creates a .reg file) 
		1. Save this file as `USB Write Potection ON`
	3. Right click on `WriteProtect` key and select Modify; change the value from 0. 
		1. Right-Click on `StorageDevicePolicies` and select Export again. 
		2. Save this .reg file on your Desktop as `USB Write Protection OFF`
	4. Now double click on either to enable and disable USB write protection. 
**8. Make a Logical acquisition of a thumb drive**
	0. Create a new folder on `Desktop` called FTKI
	1. Open FTK imager 
	2. Click `File` > `Create Disk Image`
	3. Select `Logical Drive` and click "Next" ![[Pasted image 20231009144923.png]] ![[Pasted image 20231009144946.png]]
	4. Select your USB Drive (usually will have the FAT32 file system)
	5. Add the destination for the image using the `Add` button ![[Pasted image 20231009145119.png]]
	6. You will be asked for the image type ![[Pasted image 20231009145149.png]]
		- Create a E01 image 
	7. Add info for the evidence 
		- Click next ![[Pasted image 20231009145302.png]]
	8. Browse to save image within the FTKi folder you made and name it `Pendrive-logical`
		- Click Finish 
	9. Select `Start` 
		- ![[Pasted image 20231009145359.png]] ![[Pasted image 20231009145407.png]]
		- Depending on the size of your pen drive, it takes sometimes for the image to be created 
		- After the creation of the Image you will see a screen ![[Pasted image 20231009152113.png]] 
**9. Analyse the data from the E01 file**
	1. Get a copy `usb_a.E01` 
	2. In FTK Imager click `File` > `Add Evidence Item` 
		- Then choose the `usb_a.E01` then click `next` ![[Pasted image 20231009152516.png]]
	- What is a SID folder
**10. Challenge**
	1. https://www.imagetotext.info/ converts the text to image
2E 2D 20 2E 2E 2E 20 2D 2E 2D 2E 20 2E 2E 20 2E 2E 20 2F 20 2D 2E 2D 2E 20 2E 2D 20 2D 2E 20 2F 20 2D 2E 2E 2E 20 2E 20 2F 20 2E 2E 2D 2E 20 2E 2E 2D 20 2D 2E 20 2F 20 2D 20 2D 2D 2D 20 2D 2D 2D 20 2E 2D 2E 2D 2E 2D 20 2F 20 2E 2D 20 2F 20 2E 2D 2E 2E 20 2D 2D 2D 20 2D 20 2F 20 2D 2D 2D 20 2E 2E 2D 2E 20 2F 20 2E 2D 20 2E 2D 2E 20 2D 20 2F 20 2E 2E 20 2E 2E 2E 20 2F 20 2E 2D 2D 2E 20 2E 2D 2E 20 2D 2D 2D 20 2D 2E 2E 20 2E 2E 2D 20 2D 2E 2D 2E 20 2E 20 2D 2E 2E 20 2F 20 2D 2D 2D 20 2D 2E 20 2F 20 2E 2D 20 2F 20 2D 2E 2D 2E 20 2D 2D 2D 20 2D 2D 20 2E 2D 2D 2E 20 2E 2E 2D 20 2D 20 2E 20 2E 2D 2E 20 2F 20 2D 2E 2D 2E 20 2E 2D 20 2E 2D 2E 2E 20 2E 2D 2E 2E 20 2E 20 2D 2E 2E 20 2F 20 2E 2D 20 2E 2E 2E 20 2D 2E 2D 2E 20 2E 2E 20 2E 2E 20 2F 20 2E 2D 20 2E 2D 2E 20 2D 20 2E 2D 2E 2D 2E 2D 20 2F 20 2D 2E 2D 2D 20 2D 2D 2D 20 2E 2E 2D 20 2F 20 2E 2E 2D 20 2E 2E 2E 20 2E 20 2D 2E 2E 20 2F 20 2D 20 2D 2D 2D 20 2F 20 2D 2E 2E 2E 20 2E 20 2F 20 2E 2D 20 2D 2E 2E 2E 20 2E 2D 2E 2E 20 2E 20 2F 20 2D 20 2D 2D 2D 20 2F 20 2E 2D 2D 20 2E 2D 20 2D 20 2D 2E 2D 2E 20 2E 2E 2E 2E 20 2F 20 2D 20 2E 2E 2E 2E 20 2E 20 2F 20 2E 2E 2E 20 2D 20 2E 2D 20 2E 2D 2E 20 2F 20 2E 2D 2D 20 2E 2D 20 2E 2D 2E 20 2E 2E 2E 20 2F 20 2D 2D 20 2D 2D 2D 20 2E 2E 2E 2D 20 2E 2E 20 2E 20 2F 20 2E 2E 20 2D 2E 20 2F 20 2D 20 2E 2E 2E 2E 20 2E 20 2F 20 2D 2E 2D 2E 20 2D 2D 2D 20 2D 2D 20 2D 2D 20 2E 2D 20 2D 2E 20 2D 2E 2E 20 2F 20 2E 2D 2E 2E 20 2E 2E 20 2D 2E 20 2E 20 2F 20 2D 2E 2E 2E 20 2D 2E 2D 2D 20 2F 20 2E 2E 2D 20 2E 2E 2E 20 2E 2E 20 2D 2E 20 2D 2D 2E 20 2F 20 2D 20 2E 20 2E 2D 2E 2E 20 2D 2E 20 2E 20 2D 20 2E 2D 2E 2D 2E 2D 20 2F 20 2E 2E 2E 20 2E 2D 20 2D 2E 2E 20 2E 2D 2E 2E 20 2D 2E 2D 2D 20 2F 20 2D 20 2E 2E 2E 2E 20 2E 20 2F 20 2E 2E 2E 20 2E 20 2E 2D 2E 20 2E 2E 2E 2D 20 2E 20 2E 2D 2E 20 2F 20 2E 2E 2E 2E 20 2E 2D 20 2E 2E 2E 20 2F 20 2D 2E 2E 2E 20 2E 20 2E 20 2D 2E 20 2F 20 2D 20 2E 2D 20 2D 2E 2D 20 2E 20 2D 2E 20 2F 20 2D 2E 2E 20 2D 2D 2D 20 2E 2D 2D 20 2D 2E 20 2E 2D 2E 2D 2E 2D 20 2F 20 2D 2E 2D 2D 20 2D 2D 2D 20 2E 2E 2D 20 2F 20 2D 2E 2D 2E 20 2E 2D 20 2D 2E 20 2F 20 2E 2E 2E 20 2D 20 2E 2E 20 2E 2D 2E 2E 20 2E 2D 2E 2E 20 2F 20 2E 2E 2E 20 2E 20 2E 20 2F 20 2E 2D 2D 20 2E 2E 2E 2E 20 2E 2D 20 2D 20 2F 20 2E 2E 20 2D 20 2F 20 2E 2D 2D 20 2E 2D 20 2E 2E 2E 20 2F 20 2E 2D 2E 2E 20 2E 2E 20 2D 2E 2D 20 2E 20 2F 20 2D 2E 2E 2E 20 2D 2E 2D 2D 20 2F 20 2E 2E 2E 2D 20 2E 2E 20 2E 2E 2E 20 2E 2E 20 2D 20 2E 2E 20 2D 2E 20 2D 2D 2E 20 2F 20 2E 2E 2E 2E 20 2D 20 2D 20 2E 2D 2D 2E 20 2E 2E 2E 20 2D 2D 2D 2E 2E 2E 20 2D 2E 2E 2D 2E 20 2D 2E 2E 2D 2E 20 2E 2D 2D 20 2E 2D 2D 20 2E 2D 2D 20 2E 2D 2E 2D 2E 2D 20 2E 2D 20 2E 2E 2E 20 2D 2E 2D 2E 20 2E 2E 20 2E 2E 20 2D 2D 20 2E 2D 20 2D 20 2E 2E 20 2D 2D 2D 20 2D 2E 20 2E 2D 2E 2D 2E 2D 20 2D 2E 2D 2E 20 2D 2D 2D 20 2E 2D 2E 2D 2E 2D 20 2D 2E 20 2D 2D 2E 2E`
	2. Then go to https://gchq.github.io and convert the hex to digits
		- You get morse code
		- ``.- ... -.-. .. .. / -.-. .- -. / -... . / ..-. ..- -. / - --- --- .-.-.- / .- / .-.. --- - / --- ..-. / .- .-. - / .. ... / .--. .-. --- -.. ..- -.-. . -.. / --- -. / .- / -.-. --- -- .--. ..- - . .-. / -.-. .- .-.. .-.. . -.. / .- ... -.-. .. .. / .- .-. - .-.-.- / -.-- --- ..- / ..- ... . -.. / - --- / -... . / .- -... .-.. . / - --- / .-- .- - -.-. .... / - .... . / ... - .- .-. / .-- .- .-. ... / -- --- ...- .. . / .. -. / - .... . / -.-. --- -- -- .- -. -.. / .-.. .. -. . / -... -.-- / ..- ... .. -. --. / - . .-.. -. . - .-.-.- / ... .- -.. .-.. -.-- / - .... . / ... . .-. ...- . .-. / .... .- ... / -... . . -. / - .- -.- . -. / -.. --- .-- -. .-.-.- / -.-- --- ..- / -.-. .- -. / ... - .. .-.. .-.. / ... . . / .-- .... .- - / .. - / .-- .- ... / .-.. .. -.- . / -... -.-- / ...- .. ... .. - .. -. --. / .... - - .--. ... ---... -..-. -..-. .-- .-- .-- .-.-.- .- ... -.-. .. .. -- .- - .. --- -. .-.-.- -.-. --- .-.-.- -. --..``
	3. Convert the morse code from https://morsecode.world/international/translator.html
		- ``ASCII CAN BE FUN TOO. A LOT OF ART IS PRODUCED ON A COMPUTER CALLED ASCII ART. YOU USED TO BE ABLE TO WATCH THE STAR WARS MOVIE IN THE COMMAND LINE BY USING TELNET. SADLY THE SERVER HAS BEEN TAKEN DOWN. YOU CAN STILL SEE WHAT IT WAS LIKE BY VISITING HTTPS://WWW.ASCIIMATION.CO.NZ``

# Notes