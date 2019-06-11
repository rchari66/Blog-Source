---
title: "Portforward on Windows"
date: 2019-06-11T17:48:16Z
categories: ["windows 10 networks"]
draft: false
---

# Port forward on Windows 10

```
> netsh interface portproxy add v4tov4 listenaddress=localhost listenport=8286 connectaddress=192.168.56.101 connectport=8286
```

# List all port forward rules on Windows 10
```
> netsh interface portproxy show all
```

# Delete specific port forward rule
```
> netsh interface portproxy delete v4tov4  listenaddress=localhost listenport=8286
```

# Clear all port forward rules
```
> netsh interface portproxy reset
```

Note: 
**netsh** is network shell for windows to configure routings/port forwarding(something like iptables is for linux)