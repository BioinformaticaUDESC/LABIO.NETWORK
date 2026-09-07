# Accelerator infrastructure roadmap

Hardware-family descriptions use the official NVIDIA documentation for
[A100](../references.md#r13) and
[H100](../references.md#r14). Exact throughput is intentionally omitted
until model, memory, form factor, host interconnect and application benchmarks are known.

This document separates installed resources from expected and proposed capacity.
Hardware becomes **operational** only after delivery, installation, burn-in, security
review, driver/runtime validation and scientific benchmarking.

| Resource | Quantity | Status | Intended role |
|---|---:|---|---|
| NVIDIA A100 | 3 | Expected; not yet declared operational | AI training/inference, molecular simulation and accelerated scientific workloads |
| NVIDIA H100 | To be defined in the proposal | Proposed for a future CNPq request | Large-model training/inference and high-throughput accelerated research |
| Community GPUs | Dynamic | Registered and counted only while available | Compatible, policy-approved independent workloads |

## Integration path

1. Record a private physical inventory and ownership information.
2. Install supported drivers and container runtime.
3. Validate isolation, quotas, telemetry and failure recovery.
4. Run hardware health and LABIO scientific benchmark suites.
5. Register a sanitized capability profile in the scheduler.
6. Enable limited test queues before general scientific scheduling.
7. Publish measured workload results, methodology and uncertainty.

## Public reporting

Public documentation may include model, count, accelerator memory class, benchmark
methodology and aggregated availability. It must omit serial numbers, management
addresses, rack location, private hostnames, credentials and unrestricted monitoring
endpoints.

Procurement or funding language must remain conditional until formally approved.
Any CNPq proposal, institutional agreement or supplier document should be reviewed
before excerpts are published.
