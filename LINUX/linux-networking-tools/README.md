## 🛠️ Day 2 Task — Network Discovery Script 🔩


## 📌 Objective 📡

- After learning about tools like ifconfig, netstat, ss, and dig, I wrote a simple bash script to do basic network discovery.

- This script checks my active network interface, shows open connections, and lists nearby devices on the same subnet.


```

#!/bin/bash

# Simple Network Discovery Script

# Author: Buhle Mtshali

# Date: $(date)

echo "🌐 Network Discovery Script Running..."

echo "--------------------------------------"


# 1. Show active network interfaces and IPs

echo "[+] Checking network interfaces..."

ifconfig | grep "inet "


# 2. Show open/listening ports

echo -e "\n[+] Checking open ports..."

ss -tuln

# 3. Show current active connections

echo -e "\n[+] Checking active connections..."

netstat -ant | grep ESTABLISHED

# 4. Ping sweep (simple subnet discovery)

echo -e "\n[+] Discovering devices on the subnet..."

for ip in 192.168.1.{1..10}; do

  ping -c 1 $ip &>/dev/null && echo "Host up: $ip"

done

echo -e "\n✅ Discovery complete!"

```


## 📌 How it works

1. ifconfig → grabs your IP + interface.

2. ss → lists open ports (services listening).

3. netstat → checks active TCP connections.

3. ping sweep → loops through a range of IPs in your subnet to find who’s online.


## ⚡ Run it

```
chmod +x discovery.sh

./discovery.sh

```