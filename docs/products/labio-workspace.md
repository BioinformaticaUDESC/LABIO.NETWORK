# LABIO Workspace

**Status:** operational prototype.

LABIO Workspace is the web environment used to prepare analyses, submit scientific
jobs, follow execution, inspect results and manage LABIO Credits and devices.

## Main responsibilities

- authenticate the researcher and maintain a single LABIO identity;
- create projects and prepare supported scientific applications;
- upload or reference inputs and define execution parameters;
- show cost estimates before submission;
- follow queued, assigned, running, completed and failed jobs;
- present real registered devices and aggregate public network capacity;
- expose provenance, logs and downloadable results according to permissions;
- provide guided tutorials for supported applications.

## Tutorial model

Guided Labs explain the scientific objective, required input, parameters, expected
outputs and interpretation limits. Tutorials may submit real jobs, but should clearly
mark example data, expected credit use, retention rules and whether the execution is
local, institutional or distributed.

## Integration boundary

The browser never receives database, queue or infrastructure credentials. It communicates
only with the public API over TLS using short-lived user authorization. Administrative
operations are separated from the researcher interface.
