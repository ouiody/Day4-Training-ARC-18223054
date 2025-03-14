# Day4-Training-ARC-18223054

# Network Configuration untuk Cisco Packet Tracer

### 1. Router (RTA)
```bash
enable
configure terminal
hostname RTA
enable secret class
service password-encryption
banner motd "Unauthorized access is prohibited!"
interface GigabitEthernet0/0
 description Connection to ASw-1
 ip address 128.107.20.1 255.255.255.0
 ipv6 address 2001:DB8:A::1/64
 no shutdown
 exit
interface GigabitEthernet0/1
 description Connection to ASw-2
 ip address 128.107.30.1 255.255.255.0
 ipv6 address 2001:DB8:B::1/64
 no shutdown
 exit
write memory
```

### 2. Switch (ASw-2)
```bash
enable
configure terminal
hostname ASw-2
enable secret class
service password-encryption
banner motd "Unauthorized access is prohibited!"
interface vlan 1
 description Management VLAN
 ip address 128.107.30.15 255.255.255.0
 no shutdown
exit
ip default-gateway 128.107.30.1
write memory
```

### 3. Host Configuration (Contoh: User-04)
- **IPv4:** `128.107.30.30/24`
- **Default Gateway:** `128.107.30.1`
- **IPv6:** `2001:DB8:B::30/64`
- **Gateway IPv6:** `FE80::1`

## Testing Connectivity
Run command di bawah ini:
```bash
ping 128.107.20.1
ping 128.107.30.1
ping 2001:DB8:A::1
ping 2001:DB8:B::1
```

---
**Nama:** Allodya Qonnita Arofa
**Project:** Day 4 Training ARC
