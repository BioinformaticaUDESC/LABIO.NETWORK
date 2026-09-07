# LABIO Mobile

**Status:** Android closed testing.

LABIO Mobile connects compatible Android ARM64 devices to the same LABIO account used
by the Workspace. It can display account activity and, when explicitly enabled by the
owner, contribute limited device resources to compatible scientific workloads.

## Node behavior

- registers a device using an opaque identifier;
- reports sanitized capabilities and current availability;
- requests compatible work through authenticated outbound connections;
- respects battery, charging, network, thermal and user-defined policies;
- executes only approved application packages;
- returns hashed results and execution metadata;
- receives credits only for validated useful computation.

## Suitable workloads

Mobile nodes are intended for small, independent and portable kernels such as sequence
parsing, limited alignments, k-mer operations, transformations, scoring, validation
and carefully bounded docking tasks. Large-memory, long-running or sensitive jobs are
not mobile workloads.

## Privacy

Public network statistics must aggregate device counts and broad capability classes.
They must not expose personal files, phone numbers, advertising identifiers, exact
locations, serial numbers or a direct mapping between a public user and a physical device.
