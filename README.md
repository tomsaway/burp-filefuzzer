# Burp File Fuzzer
This extension generates synthetic files of different types by appending random bytes to file headers.
It is based on my CLI fuzzer, [httpfuzz](https://github.com/joncooperworks/httpfuzz).
Burp File Fuzzer should be used with Burp Intruder to quickly determine what file types can be uploaded.

## Installation
Installation is simple: download the 
[jar](https://github.com/JonCooperWorks/burp-filefuzzer/releases/download/alpha-0.0.1/burp-filefuzzer-alpha-0.0.1.jar)
and install it into Burp using the Extender tab.

![Installing using Burp Extender](./images/burpextender.png)


## Usage
Burp File Fuzzer will generate files of different types.
It provides three payload generators: one that generates files, one that generates MIME types and one that generates 
filenames.

![Selecting the appropriate payload generator](./images/bundled%20payload%20generators.png)

It should be used in Pitchfork mode with injection points placed on the file and filename.
This will cause Burp File Fuzzer to generate synthetic files and appropriate filenames and mime types.

![Pitchfork mode in Burp Intruder](./images/pitchfork.png)

Set the payload set according to the position of your filename and file contents.
The filename will usually be first in multipart requests.
![Selecting extension generated payloads for each payload set](./images/payload%20sets%20extension%20generated.png)

Payloads for both filenames and synthetic files should be extension generated by Filename Generator and File Generator
respectively.

![File Fuzzer creates Extension-generated payloads](./images/select%20payload%20generator.png)

For best results, disable URL encoding for filenames to prevent the "." in filenames from being URL encoded.

![Disable URL encoding for filenames](./images/disable%20URL%20encoding.png)

File Generator will add a tab to Burp's UI that allows you to set the payload size and base filename.
![Burp UI tab](./images/burpuitab.png)
## Warning
Only use this extension on targets that you have full permission to test.
I am not responsible for anything stupid, immoral or illegal you do with this.