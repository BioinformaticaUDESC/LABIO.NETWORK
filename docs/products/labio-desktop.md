# LABIO Desktop

**Status:** architecture and prototype planning.

LABIO Desktop is the workstation node for Windows, Linux and macOS. It is intended for
research computers, laboratory workstations and personal systems whose owners choose
to contribute idle CPU, memory or supported accelerators.

## Planned capabilities

- sign in with the same LABIO account used by Mobile and Workspace;
- register, rename, pause and revoke a device;
- configure CPU, memory, GPU, schedule, idle-only and temperature limits;
- download only signed and approved application artifacts;
- execute jobs in an isolated runtime appropriate to the operating system;
- show local activity, resource use, completed jobs and earned credits;
- update safely without changing the user's contribution policy.

## Platform direction

| Platform | Initial execution direction |
|---|---|
| Linux x86-64/ARM64 | OCI containers or restricted native worker |
| Windows x86-64 | isolated worker, with container support where available |
| macOS Apple Silicon | signed native or portable workloads |
| macOS Intel | limited x86-64 compatibility profile |

Platform support is published only after packaging, security, benchmark and recovery
tests are complete.
