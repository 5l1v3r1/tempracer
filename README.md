# tempracer

TempRacer

My first public release.

Race conditions are a pentesters friend. I found them pretty useful for privilege escalation, but struggled in finding a tool that would automate the process for me. So I ended up writing one. It is written in C# and the code is open source on Github. The code itself is not using that many ressources because it relies on callbacks from the OS. You can keep it running during the whole day. I found it very successful in environments where automated patching systems like BigFix are running. If you are able to trigger updates or new software installs you should give it a try. 

In my case I watched for *.bat file creation and tried to inject "add user" to it, so that my I would get local admin privs. 
	
Usage example:

tempracer.exe C:\ *.bat

Test it via:

echo "test123" > C:\temp\not-evil.bat

type C:\temp\not-evil.bat


If successful it will inject the code to add the user "alex" with password "Hack123123" and add him to the local administrator group. It will also block the file for further changes, so our evil code stays inside. I will create a dynamic version with different injects soon. Until then you have to create the binary yourself.

Download:
https://github.com/realalexandergeorgiev/tempracer/releases

Screenshot here:
![ScreenShot](http://abload.de/img/tempracer5xri7.png)


Alexander Georgiev

alexander.georgiev -a-t- daloo.de
