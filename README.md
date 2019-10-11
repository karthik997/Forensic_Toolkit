
## This contains the mostly used tools for forensic investigation
## Tools used for Basic Analysis::

Whenever you get any file, first do the initial analysis using these command line tools. 

|Tool|Description|Usage|
|-----|-------------|-------|
|file|Checks the type of file|file -filename|
|exiftool|Gives the basic metadata|exiftool - filename |
|binwalk|Shows the embedded files| binwalk -filename |
|strings | Gives out all printable characters | strings -filename |
|foremost | Extracts out any embedded files | foremost -filename |
|pngcheck | Details about a png image | pngcheck –options -filename |
|ffmpeg | Check the integrity of audio files | ffmpeg –options -filename |

## Steganography Detection Tools:

These are some tools which detect if any stegnano activity is being done on any kind of file:

| Tool | File Types Supported | Usage | 
|------|----------------------|-------|
|zsteg | PNG,BMP | zsteg -filename|
|stegdetect| JPG | stegdetect -filename |
|stegbreak | JPG | stegbreak -t o -f wordlist.txt -filename|
|stegsolve | All image format | *Detail is mentioned below* |

**First install the jar package of stegsolve and then use it as follows: [java -jar stegsolve] in Terminal.**

**Make sure you install the required java package also**

## Steganography Application Tools: 

These tools could be used to implement as well as reveal any hidden messages.One can try any of these tools if they feel that one of these techniques have been implemented to hide any message. 

| Tool | File Types Supported| Hiding | Recovering |
|------|---------------------|--------|------------|
|Jsteg | JPG |  jsteg hide hide.jpg secret.txt image1.jpg | jsteg reveal hide.jpg output.txt
|OpenStego| PNG | openstego embed -mf secret.txt -cf hide.png -p password -sf stego.png | openstego extract -sf openstego.png -p ab12 -xf output.txt|
|Outguess| JPG | outguess -k password -d secret.txt cover.jpg stego.jpg | outguess -r -k password stego.jpg output.txt |
|Steghide| JPG,BMP,WAV | steghide embed -f -ef secret.txt -cf cover.jpg -p password -sf stego.jpg | steghide extract -sf stego.jpg -p password -xf output.txt | 
|LSBSteg| PNG,BMP | LSBSteg encode -i cover.png -o stego.png -f secret.txt | LSBSteg decode -i stego.png -o output.txt |
|mp3stego|Audio files| mp3stego-encode -E secret.txt -P password cover.wav stego.mp3 | mp3stego-decode -X -P password stego.mp3 out.txt | 
|AudioStego| Audio files| hideme cover.mp3 secret.txt && mv ./output.mp3 stego.mp3 | hideme stego.mp3 -f && cat output.txt|
|stegano|PNG| stegano-lsb hide --input cover.jpg -f secret.txt -e UTF-8 --output stego.png or stegano-red hide --input cover.png -m "secret msg" --output stego.png or stegano-lsb-set hide --input cover.png -f secret.txt -e UTF-8 -g $GENERATOR --output stego.png for various generators (stegano-lsb-set list-generators)| stegano-lsb reveal -i stego.png -e UTF-8 -o output.txt or stegano-red reveal -i stego.png or stegano-lsb-set reveal -i stego.png -e UTF-8 -g $GENERATOR -o output.txt|


## Tools dealing with Audio files(Embedding and Revealing Data):

| Tool | Description | Usage|
|------|-------------|------|
|Audacity| This is a great tool in analysing, modifying and revealing any data present inside audio, mostly used in analysing audio files| audacity -filename| 
|Sonic Visualiser| Yet another similar tool like Audacity, which also cud be used in investigating audio files| sonic-visualiser -filename|
|Deepsound| This is a tool which is used to hide/reveal any data in audio file using a password| It is a Windows apllication |

**mp3stego and Audiostego are also tools which could be used for Audio data analysis.**

**Deepsound is a Windows based application, which can be downloaded from Internet.**

(Pssss.. Just check my Tool_Vault maybe you can find one) :grin: 


## Tool dealing with Memory Dumps(Analysing hidden data or malicious activity):

Volatility is an open source memory forensics framework for incident response and malware analysis. It is written in Python and supports Microsoft Windows, Mac OS X, and Linux.

To download volatility just type in the terminal  **sudo apt-get install volatility**

## Tools dealing with Network Packet captures(Analysing network activity):

|Tool| Description | Usage|
|----|-------------|------|
|Wireshark| Wireshark is a free and open source packet analyzer. It is used for network troubleshooting, analysis, software and communications protocol development | wireshark filename.pcap|
|Tcpdump| tcpdump is a common packet analyzer that runs under the command line. It allows the user to display TCP/IP and other packets being transmitted or received over a network to which the computer is attached | tcpdump -options |
|Network Miner| NetworkMiner is a Network Forensic Analysis Tool (NFAT) for Windows. NetworkMiner can be used as a passive network sniffer/packet capturing tool in order to detect operating systems, sessions, hostnames, open ports etc. without putting any traffic on the network | GUI application|

**Network Miner is a GUI Application which can be downloaded from Internet Or just check my Vault...** :grin:

## Tools used for Disk-Image data Analysis:

| Tool | Description | Usage |
|------|-------------|-------|
|Fdisk| For computer file systems, fdisk is a command-line utility that provides disk partitioning functions | fdsik -lu filename|
|mmls | mmls displays the contents of a volume system (media management). In general, this is used to list the partition table contents so that you can determine where each partition starts. The output identifies the type of partition and its length, which makes it easy to use 'dd' to extract the partitions| mmls filename |
|TestDisk| Testdisk is powerful free data recovery software. It was primarily designed to help recover lost partitions and/or make non-booting disks bootable again when these symptoms are caused by faulty software | testdisk filename|
|Autopsy| Autopsy is computer software that makes it simpler to deploy many of the open source programs and plugins used in The Sleuth Kit. The graphical user interface displays the results from the forensic search of the underlying volume making it easier for investigators to flag pertinent sections of data| GUI Application|
|OSForensics| OSForensics is a digital computer forensic application which lets you extract and analyse digital data evidence efficiently and with ease. It discovers, identifies and manages ie uncovers everything hidden inside your computer systems and digital storage devices. | GUI Application | 

**Both Autopsy and OSForensics can be downloaded from Internet or check in my Vault!!!!!!!** 









