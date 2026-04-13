# DaltoCCNA - issue during lab
VLAN & Inter-VLAN Routing Lab / 01-basic office
## Overview
This lab focuses on configuring VLANs, trunking between switches, and inter-VLAN routing using a router-on-a-stick setup.

## Topology
- 1 Router
- 2 Switches
- 2 PCs
- VLAN 10 and VLAN 20
- Subnetting using /25

## Issue Encountered
After completing the configuration, PC1 was able to ping its default gateway but was unable to reach PC2.

From PC2, attempts to ping its default gateway also failed.

## Troubleshooting Process
- Verified PC IP addressing (IP, subnet mask, default gateway)
- Checked VLAN assignments on access ports
- Verified trunk configuration between switches and router
- Confirmed router subinterfaces were correctly configured and operational

All configurations appeared correct.

## Root Cause
PC2 was connected to the wrong switch port.

It was plugged into **Fa0/3**, while VLAN 20 was configured on **Fa0/2**.

## Resolution
Moved PC2 to the correct interface (**Fa0/2**).

## Result
- PC2 successfully reached its default gateway
- Inter-VLAN communication between PC1 and PC2 worked as expected

## Key Takeaways
- Always verify physical connections before assuming configuration issues
- Use a structured troubleshooting approach (Layer 1 → Layer 3)
- A working default gateway ping helps isolate the issue scope
