# 🌐 Today's Learning: How the Internet Works  

When we type something like `google.com` into a browser, a fascinating chain of processes happens in milliseconds. Here’s what I explored today 👇  

---

## 📌 Key Learnings  

- **Internet Flow** → From request to response, data travels in **packets** across routers, switches, and servers.  
- **Packets** → Small chunks of data that contain: source & destination IPs, MAC addresses, port numbers, and payload (the actual data).  
- **IP Address** → Unique numerical address that identifies a device on a network (like your home’s address).  
- **MAC Address** → A permanent hardware ID given to your device’s network card. Used only inside local networks (LAN).  
- **Public vs Private IPs** →  
  - **Private IP**: Used inside home/office networks (e.g., `192.168.x.x`, `10.x.x.x`).  
  - **Public IP**: Provided by ISP, used to communicate with the outside internet.  
  - **NAT (Network Address Translation)**: Converts private IPs into a single public IP when going online.  

---

## 🌍 DNS (Domain Name System)  

DNS works like the **phonebook of the internet**. It translates human-friendly domain names (`google.com`) into machine-friendly IP addresses.  

### 🧩 Types of DNS Servers  

1. **Recursive Resolver (DNS Recursor)**  
   - First stop when you type a domain in the browser.  
   - Works like a detective 🕵️, finding the IP address on your behalf.  
   - Steps:  
     - Checks **local cache**.  
     - If not found → asks the **Root Server**.  
     - Then queries the **TLD Server**.  
     - Finally, reaches the **Authoritative Server**.  
     - Returns the IP to your browser.  

2. **Root Server**  
   - The "starting point" of DNS queries.  
   - Knows where to find the **TLD servers**.  
   - Example: For `google.com`, it tells the resolver to check `.com` TLD servers.  

3. **TLD Server (Top-Level Domain Server)**  
   - Handles specific domain extensions like `.com`, `.org`, `.net`.  
   - Directs queries to the correct **Authoritative Server**.  

4. **Authoritative DNS Server**  
   - The final source of truth.  
   - Holds the actual IP mapping of a domain.  
   - Example: `google.com → 142.250.190.14`.  

---

## 🛠️ Other Networking Components  

- **Router** → Connects different networks and forwards data packets.  
- **Switch** → Connects multiple devices in a LAN and forwards data within the same network.  
- **DHCP (Dynamic Host Configuration Protocol)** → Automatically assigns IP addresses to devices in a network.  
- **VPN (Virtual Private Network)** → Creates a secure tunnel between your device and the internet, hiding your IP and encrypting traffic.  

---

## ⚡ Fun Fact  

Every time we hit **Enter** in the browser, a full detective investigation happens in the background — and all of this completes in **milliseconds**!  

---

### 🏷️ Tags  
#Internet #DNS #Networking #LearningJourney #TechExplained
