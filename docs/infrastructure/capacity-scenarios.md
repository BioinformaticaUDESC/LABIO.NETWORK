# Capacity scenarios

The following scenarios explain how LABIO.NETWORK may scale. They are planning models,
not claims about installed infrastructure or guaranteed throughput.

## Comparison

| Dimension | 100,000 smartphones | 100 Linux servers |
|---|---|---|
| Resource profile | highly heterogeneous ARM64 edge devices | comparatively stable CPU/GPU nodes |
| Availability | intermittent; user, battery, heat and network dependent | scheduled and usually predictable |
| Best workload | many small independent tasks | long, memory-heavy or accelerator-dependent jobs |
| Data policy | public or explicitly eligible data | institutional and policy-controlled data |
| Runtime | approved native/portable kernels | OCI containers and optimized native tools |
| Failure model | frequent disconnect and requeue | lower churn, planned maintenance |
| Network | variable mobile/residential links | higher and more stable bandwidth |
| Validation | stronger redundancy for untrusted nodes | trust tier plus application validation |

## Smartphone scenario

For `N = 100,000` registered smartphones, capacity depends on how many are simultaneously
eligible. If each eligible phone contributes `c` logical cores and the measured
availability factor is `A`, the effective concurrent core count is:

```text
C_mobile = N × c × A
```

An illustration with two contributed cores and `A = 0.25` gives 50,000 effective
concurrent logical cores. This is not equivalent to 50,000 server cores: instruction
sets, sustained performance, memory, thermal limits and runtime efficiency differ.

For an independently partitionable application, measured throughput is more useful:

```text
tasks_per_day = Σ (86,400 × availability_i × efficiency_i) / benchmark_time_i
```

The scheduler must use per-device-class benchmarks rather than marketing TFLOPS.

## Server scenario

For `S = 100` servers, each with `c_s` schedulable CPU cores, `g_s` compatible GPUs and
availability `A_s`:

```text
CPU_capacity = Σ (c_s × A_s)
GPU_capacity = Σ (g_s × A_s × workload_efficiency_s)
```

No fixed core or GPU total is claimed because server configurations have not been
specified here. Once machines are known, the inventory should publish ranges and
measured scientific throughput without revealing management details.

## Hybrid network

The strongest design combines both groups:

- smartphones process short, independent and non-sensitive kernels;
- desktop nodes handle medium workloads and opportunistic acceleration;
- Linux servers handle large-memory, long-running, GPU and restricted workloads;
- A100/H100 pools accelerate compatible AI and scientific applications;
- the scheduler partitions campaigns according to compatibility, trust and cost;
- validation and provenance make results comparable across heterogeneous nodes.

## Required benchmarks

Report application-level results such as dockings/hour, reads/second,
sequences/second, GROMACS ns/day, assemblies/day and validated inference throughput.
Every published result should include software version, dataset, parameters, node
class, sample size, variability and energy/thermal policy when relevant.
