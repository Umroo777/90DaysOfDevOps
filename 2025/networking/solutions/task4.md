### 4. **Hands-On with Networking Commands**
- Practice essential networking commands like:
   `ping` (check connectivity)
   `traceroute` / `tracert` (trace packet routes)
   `netstat` (network statistics)
   `curl` (make HTTP requests)
  `dig` / `nslookup` (DNS lookup)


# 🌐 Networking Commands Cheat Sheet for DevOps

This guide provides a quick reference to essential networking commands used in daily DevOps and Linux system administration tasks.

---

## 1. 🔍 `ping` – Check Network Connectivity

**Purpose:** Test if a host is reachable over the network.


ping google.com
```

- Sends ICMP echo requests to a host
- Useful for basic connectivity checks

**Flags:**
- `-c 4`: Send 4 packets only  
  `ping -c 4 google.com`

---

## 2. 🛰️ `traceroute` / `tracert` – Trace Route of Packets

**Purpose:** Display the path packets take to a destination.


traceroute google.com      # Linux/macOS
tracert google.com         # Windows
```

- Shows each hop between your system and the target
- Useful for diagnosing network delays or routing issues

---

## 3. 📊 `netstat` – Network Statistics

**Purpose:** Show active connections, listening ports, and routing tables.

```bash
netstat -tuln
```

- `-t`: TCP connections  
- `-u`: UDP connections  
- `-l`: Listening ports  
- `-n`: Numeric output (IP/port)

**Alternative on newer systems:**

```bash
ss -tuln
```

---

## 4. 🌐 `curl` – Transfer Data from URLs

**Purpose:** Interact with APIs or web servers from the command line.

```
curl http://example.com
```

**Common use cases:**
- Test REST APIs
- Download files
- Send headers or data

``
curl -I http://example.com      # Fetch headers only
curl -X POST -d "name=umar" http://example.com/api
```

---

## 5. 🧠 `dig` – DNS Lookup

**Purpose:** Query DNS records of a domain.

```
dig google.com
```

- Shows A records (IP addresses) by default
- Can be used to check other record types:


dig google.com MX     # Mail exchange records
dig google.com NS     # Name servers
```

---

## 6. 🔎 `nslookup` – DNS Lookup (Alternative to `dig`)

**Purpose:** Resolve domain names to IP addresses (Windows-friendly)

nslookup google.com
```

- Also used for reverse DNS lookups (IP → Domain)

---

## 📌 Summary Table

| Command     | Purpose                          | Example Usage                        |
|-------------|----------------------------------|---------------------------------------|
| `ping`      | Test connectivity                | `ping google.com`                     |
| `traceroute`| Trace packet route               | `traceroute google.com`              |
| `netstat`   | Show connections & listening ports| `netstat -tuln`                      |
| `curl`      | HTTP requests                    | `curl -I http://example.com`         |
| `dig`       | DNS queries                      | `dig google.com MX`                  |
| `nslookup`  | DNS lookup                       | `nslookup google.com`                |


> 🧠 Pro Tip: Combine these commands during troubleshooting to pinpoint network and connectivity issues quickly