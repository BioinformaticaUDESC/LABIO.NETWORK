# LABIO.NETWORK ecosystem

**Status:** evolving architecture with operational prototypes.

LABIO.NETWORK separates the services that coordinate work from the devices that
execute scientific workloads. A single account can submit jobs in the Workspace,
observe its devices and use or earn LABIO Credits. Resource contribution remains
voluntary and policy-controlled.

```text
Researcher
   |
   v
LABIO Workspace ---- LABIO AI
   |                    |
   +---------+----------+
             v
       Control Plane
  identity | API | scheduler
  queue | registry | credits
             |
     +-------+--------+----------------+
     |                |                |
     v                v                v
LABIO Mobile    LABIO Desktop    LABIO Server
Android ARM64   Win/Linux/macOS  Linux/containers
     |                |                |
     +----------------+----------------+
                      v
          validation and provenance
                      |
                      v
                   results
```

## Logical components

| Component | Responsibility |
|---|---|
| Identity | User authentication, account linking and scoped authorization |
| Device registry | Device registration, capabilities and availability |
| Application registry | Approved, versioned and signed scientific runtimes |
| Scheduler | Matches jobs to compatible and authorized resources |
| Queue | Durable job state and delivery coordination |
| Credits ledger | Records validated resource use and contribution |
| Result service | Stores outputs, provenance and validation state |
| Observability | Aggregated metrics, logs and operational alerts |

## Trust boundaries

Users, devices, applications, data and results are separate security domains.
Authentication in one domain does not grant unrestricted access to another. Nodes
request work through authenticated outbound connections; the platform does not need
unsolicited inbound access to a participant's home or institutional network.

## Public versus private architecture

This repository contains logical flows, interfaces, compatibility rules and sanitized
deployment examples. Production credentials, internal addresses, administrative
routes, user records and exact physical topology belong in private operational systems.
