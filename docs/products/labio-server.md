# LABIO Server

**Status:** architecture and prototype planning.

LABIO Server is the Linux-first node for dedicated servers, GPU systems, laboratory
clusters and institutional infrastructure. It differs from LABIO Desktop by supporting
unattended operation, larger queues, multiple execution slots and institutional policy.

## Initial target

- Linux x86-64, followed by Linux ARM64;
- system service with outbound authenticated communication;
- OCI-compatible isolated scientific workloads;
- NVIDIA GPU discovery through an approved container runtime;
- CPU, memory, GPU, storage and concurrency quotas;
- maintenance windows, reservations and institution-first scheduling;
- structured health, benchmark and provenance reports;
- graceful drain before maintenance or shutdown.

## Technical contract

| Concern | Public requirement |
|---|---|
| Runtime identity | Immutable application version and content digest |
| Enrollment | Institution-approved node identity and scoped credential |
| Isolation | Rootless container or equivalent boundary with explicit limits |
| Accelerators | Declared device type, memory and runtime compatibility |
| Storage | Per-assignment workspace with retention and secure cleanup policy |
| Operations | Health, capacity, assignment and result telemetry without raw secrets |

Container artifacts should use content-addressed, multi-platform metadata compatible
with the [OCI Image Specification](../references.md#r4).
Institutional queue admission can draw on Kubernetes-native quota and fair-sharing
concepts documented by [Kueue](../references.md#r10).

## Institutional mode

An institution can define resource pools, project quotas, trusted data classes and
priority policies without exposing management interfaces publicly. Kubernetes and
batch-system adapters may be added behind the same scheduler contract.

## Secure enrollment

Server enrollment uses short-lived bootstrap authorization and produces a revocable
device identity. Private keys, management IPs, inventory serials and monitoring
credentials are never committed to this repository.
