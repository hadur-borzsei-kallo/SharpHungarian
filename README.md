# SharpHungarian

This is an unifished console app for defeating EDR, defeating internal centralised loggin, and using Virustotal as an outbound command and control channel for C2

Once you get DA in a network, the steps are as follows - .

1. Upload any text file to VirusTotal (after getting an API key), then take the SHA1 hash generated by VirusTotal

2. Run SharpHungarian - (Make Your Fortress INSIDE the network):   SharpHungarian.exe VirusTotalApi Sha1hash DAUSER DAPASSWORD

This will then do the following - 

#It will add the assembly to the registry to run on start up so that reboots are ineffective to some degree
#It will enable a firewall on the machine to block all internal network access, and prevent all internal Administrative access to the machine (TODO)
#It will open a port through the firewall on port 443 (TODO)
#It will then run the whoami command, and use the VirusTotal HTTPS API to communicate over comments on the particular SHAI file that you uploaded
Then return output etc...

Most of the code is done, however some code needs to be finished by someone more studious than myself :D
I have also added a link to a C++ library that will turn the process into a Protected Process much the same as AV/EDRs run on Windows (link included in in-code comment) so you need to compile the lib and then import and communicate with the dll - add p/invoke signatures https://docs.microsoft.com/en-us/dotnet/api/system.runtime.interopservices.dllimportattribute?redirectedfrom=MSDN&view=netcore-3.1

It was an idea I had over the last couple of days, and spent a short morning putting it together, so needs to be finished collaboratively.

Enjoy Red Team :)


*** DISCLAIMER ***

The authors are not responsible for the consequences of use of this software, no matter how awful, even if they arise from flaws in it.

There is no warranty against interference with your enjoyment of the library or against infringement. There is no warranty that our efforts or the library will fulfill any of your particular purposes or needs. This library is provided with all faults, and the entire risk of satisfactory quality, performance, accuracy, and effort is with the user.
