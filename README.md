# BridgeNet Campus: University Network in Cisco Packet Tracer

CSE421 (Computer Networks) lab term project, BRAC University, Summer 2026.

A complete campus network for a university with six departments (CSE, EEE, BBA, Pharmacy, LAW, Research), built and tested in Cisco Packet Tracer.

## What the network does

- **Topology:** six departmental routers, each with its own LAN switch, two PCs and a network printer. CSE, EEE and BBA share a backbone switch; CSE has direct serial links to Pharmacy, LAW and Research, and LAW–Research has a backup link.
- **Addressing:** VLSM plan carved out of `10.12.0.0/16`, sized to each department's user count (CSE /23 down to /30 point-to-point links).
- **Routing:** RIPv2 with redistribution between CSE, EEE and BBA; static routing elsewhere: a default route on Pharmacy, recursive next-hop routes on LAW, directly attached routes on Research.
- **Failover:** floating static routes so LAW and Research reroute through each other when their link to CSE goes down.
- **Services:**
  - central DNS server in CSE
  - web servers for `www.eee.nbu.edu` and `www.research.nbu.edu`
  - mail servers for `cse.nbu.edu` and `bba.nbu.edu` with cross-domain email
  - DHCP from the CSE router (with relay on EEE, BBA, Pharmacy) plus dedicated DHCP servers in LAW and Research

## Files

| File | Contents |
|---|---|
| `2308_BridgeNet_Campus.pkt` | The Packet Tracer network (open with Cisco Packet Tracer 8.x) |
| `docs/Topology_Diagram.pdf` | Labelled topology with interfaces, networks, primary and backup links |
| `docs/VLSM_AddressTable_Config_Assumptions.pdf` | Base network derivation, VLSM tree, subnetting and address tables, configuration commands, assumptions |
| `docs/Work_Distribution.pdf` | Which group member did which part |

These are the files submitted for the project. Other group members' student IDs have been blacked out.

## My part

I configured the servers and end devices: the central DNS server and its records, both web servers, both email servers with their domains and user accounts, the LAW and Research DHCP servers, static addressing for the printers, DHCP on the PCs, and the mail clients.

## Team

Group 2308: Md. Asraful Islam Emon, Shuvo Datta, Minhaz Uddin, Ashfia Haque.
