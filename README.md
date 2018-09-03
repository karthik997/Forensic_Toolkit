
## THis contains the mostly used tools for forensic investigation
*****************************************************************
## Tools used for Basic Analysis:

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

**First install the jar package of stegsolve and then use it as follows: [java -jar stegsolve] in Terminal. 
** Make sure you install the required java package also  

## Steganography Application Tools: 

These tools could be used to implement as well as reveal any hidden messages.One can try any of these tools if they feel that one of these techniques have been implemented to hide any message. 

| Tool | File Types Supported| Hiding | Recovering |
|------|---------------------|--------|------------|
|Jsteg | JPG |  jsteg hide hide.jpg secret.txt image1.jpg | jsteg reveal hide.jpg output.txt
|OpenStego| PNG | openstego embed -mf secret.txt -cf hide.png -p password -sf stego.png | openstego extract -sf openstego.png -p ab12 -xf output.txt|
|Outguess| JPG | outguess -k password -d secret.txt cover.jpg stego.jpg | outguess -r -k password stego.jpg output.txt |
|Steghide| JPG,BMP,WAV | steghide embed -f -ef secret.txt -cf cover.jpg -p password -sf stego.jpg | steghide extract -sf stego.jpg -p password -xf output.txt | 
|LSBSteg| PNG,BMP | LSBSteg encode -i cover.png -o stego.png -f secret.txt | LSBSteg decode -i stego.png -o output.txt |


## Tools dealing with Audio files(Embedding and Revealing Data):

| Tool | Description | Usage|
|------|-------------|------|
|Audacity| This is a great tool in analysing, modifying and revealing any data present inside audio, mostly used in analysing audio files| audacity -filename| 
|Sonic Visualiser| Yet another similar tool like Audacity, which also cud be used in investigating audio files| sonic-visualiser -filename|
|Deepsound| This is a tool which is used to hide/reveal any data in audio file using a password| It is a Windows apllication |

**Deepsound is a Windows based application, which can be downloaded from Internet.(Pssss.. Just check my Tool_Vault maybe you can Find one ;-) 








