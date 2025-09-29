# Lab 01 - VLANs Basic

## Objective
- Practise creating VLANs on a switch.
- Assign switchports to VLANs
- Configure IP addresses on VPCs in different VLANs.
- Verify connectivity within and across VLANs

## Topology
- 1 Switch
- 6 PCs (VPC1-VPC6)
- VLANs: 10, 20, 30
- Each VLAN has 2 PCs. 

(Diagram: see diagram.png)

## Configuration Summary

### VLAN to VPC Mapping

| VLAN | Subnet           | VPCs Assigned  |
|------|------------------|----------------|
| 10   | 192.168.10.0/24 | VPC1 (192.168.10.2), VPC2 (192.168.10.3) |
| 20   | 192.168.20.0/24 | VPC3 (192.168.20.2), VPC4 (192.168.20.3) |
| 30   | 192.168.30.0/24 | VPC5 (192.168.30.2), VPC6 (192.168.30.3) |

(See `configs/` for full device configs)

## Verification
- Commands used:  
  - `show vlan`, `show vlan brief`, `show vlan summary`  
  - `show vlan id [id-num]`, `show vlan name [vlan-name]`  

- Results:  
  - VLANs correctly appeared in `show vlan brief`.  
  - PCs in the same VLAN could ping each other (✅ success).  
  - PCs in different VLANs could not ping each other (expected).  

## Lessons Learned
- VLANs segment broadcast domains at Layer 2.  
- PCs in different VLANs cannot talk to each other without a Layer 3 device (router-on-a-stick or L3 switch).  
- Good practice to use `show vlan brief` to quickly confirm port assignments.  