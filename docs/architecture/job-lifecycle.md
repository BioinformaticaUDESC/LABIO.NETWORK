# Scientific job lifecycle

**Status:** operational prototype, with validation and policy layers evolving.

```text
prepare -> authenticate -> submit -> validate input -> classify data
        -> estimate cost -> enqueue -> match node -> reserve
        -> execute in isolation -> upload result -> validate
        -> record provenance -> settle credits -> expire temporary files
```

## Stages

1. The researcher prepares an approved application and parameters in LABIO Workspace.
2. The API authenticates the account and checks project permissions and credit limits.
3. Inputs receive hashes and a data classification before scheduling.
4. The scheduler selects only nodes compatible with the application, architecture,
   memory, accelerator, reliability and data policy.
5. The node obtains a short-lived assignment and executes it in an isolated working
   directory with explicit CPU, memory, storage and time limits.
6. Outputs are hashed, uploaded and validated according to the application profile.
7. The provenance record links application version, input hashes, parameters, node
   class, runtime and validation state.
8. Credits are debited from the requester and awarded for validated useful work.
9. Temporary input and execution files are deleted according to the published
   retention policy; durable results follow project policy.

The provenance record should represent inputs, execution and responsible actors in a
machine-readable form aligned with [W3C PROV-O](../references.md#r3).

## Failure handling

Disconnected or constrained nodes are normal. Assignments use leases and heartbeats.
Expired work can be requeued, while late or duplicated results are handled
idempotently. High-value jobs may use redundant execution or trusted institutional
nodes.

## Data restrictions

Public, non-sensitive research data may be eligible for community execution.
Restricted, clinical, identifiable or regulated data must remain on approved
institutional infrastructure under the relevant governance policy.
