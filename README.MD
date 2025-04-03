# Network Design for Trading Floor Support Centre

## Project Overview
This project involves designing and implementing a hierarchical, redundant network for a trading floor support center moving to a new three-floor building with 600 staff members across six departments.

## Network Requirements

### Building Layout
- **First Floor**:
  - Sales and Marketing Department (120 users)
  - Human Resource and Logistics Department (120 users)
  
- **Second Floor**:
  - Finance and Accounts Department (120 users)
  - Administrator and Public Relations Department (120 users)
  
- **Third Floor**:
  - ICT Department (120 users)
  - Server Room (12 devices)

## Network Design

### Topology
Three-layer hierarchical model:
1. **Core Layer**: Dual routers
2. **Distribution Layer**: Dual multilayer switches
3. **Access Layer**: Departmental switches

### IP Addressing
   Base network: `172.16.1.0/16`
   
   Subnetting was performed to allocate appropriate IP ranges to each department while allowing for future growth. The server room devices use static IP addressing while all other devices obtain addresses via DHCP.

### VLAN Configuration
   Each department is assigned to a separate VLAN with corresponding subnet:
| Department                     | VLAN ID | Subnet           |
|--------------------------------|---------|------------------|
| Sales and Marketing            | 10      | 172.16.10.0/24   |
| Human Resource and Logistics    | 20      | 172.16.20.0/24   |
| Finance and Accounts           | 30      | 172.16.30.0/24   |
| Admin and Public Relations     | 40      | 172.16.40.0/24   |
| ICT                            | 50      | 172.16.50.0/24   |
| Server Room                    | 60      | 172.16.60.0/28   |

### Technologies Implemented
1. **Redundant Architecture**
    - Dual routers and multilayer switches
    - Dual ISP connections (195.136.17.0/30 and 195.136.17.4/30)
2. **Routing**
    - OSPF routing protocol for dynamic route advertisement
    - Inter-VLAN routing on multilayer switches
3. **Security**
    - SSH for secure remote access
    - Port security (Finance department)
    - ACLs for traffic control
4. **Services**
    - DHCP for dynamic IP allocation
    - PAT for Internet access
    - Wireless networks per department
5. **Management**
    - Basic device hardening (passwords, banners)
    - Disabled IP domain lookup

---
```bash
    Password : cisco
```


- For more Details vist :
`https://gurutechnetworks.otombenard.com/assetsProject/project6`


