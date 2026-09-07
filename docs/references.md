# Technical references

This bibliography records the external standards and primary documentation used to
shape the public LABIO.NETWORK architecture. A reference indicates architectural
alignment; it does not claim certification, compliance or production deployment.

## Identity, trust and software supply chain

<a id="r1"></a>
### R1 — NIST SP 800-207

National Institute of Standards and Technology. *Zero Trust Architecture*, 2020.
[Official publication](https://csrc.nist.gov/pubs/sp/800/207/final).

Used for the principle that network location or device ownership does not create
implicit trust.

<a id="r2"></a>
### R2 — OpenID Connect Core 1.0

OpenID Foundation. *OpenID Connect Core 1.0 incorporating errata set 2*.
[Official specification](https://openid.net/specs/openid-connect-core-1_0-18.html).

Used as the identity layer for interoperable authentication and account linking.

<a id="r3"></a>
### R3 — W3C PROV-O

World Wide Web Consortium. *PROV-O: The PROV Ontology*, W3C Recommendation, 2013.
[Official recommendation](https://www.w3.org/TR/prov-o/).

Used as a conceptual basis for entities, activities and agents in scientific
provenance records.

<a id="r4"></a>
### R4 — OCI Image Specification

Open Container Initiative. *Image Manifest Specification*.
[Official specification](https://specs.opencontainers.org/image-spec/manifest/).

Used for content-addressable, multi-platform scientific runtime artifacts.

<a id="r5"></a>
### R5 — SLSA

Open Source Security Foundation. *Supply-chain Levels for Software Artifacts*.
[Official specification](https://slsa.dev/spec/).

Used as a reference for build provenance and increasing artifact assurance.

<a id="r6"></a>
### R6 — OAuth 2.0 for Native Apps

IETF. *RFC 8252: OAuth 2.0 for Native Apps*, 2017.
[Official RFC](https://www.rfc-editor.org/info/rfc8252/).

Used for browser-based authorization flows in LABIO Mobile and Desktop rather than
embedded credential collection.

## Scientific AI and reproducibility

<a id="r7"></a>
### R7 — Retrieval-Augmented Generation

Lewis et al. *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks*,
NeurIPS 2020. [Primary paper](https://papers.neurips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html).

Used as the foundational citation for retrieval-conditioned generation in LABIO AI.

<a id="r8"></a>
### R8 — FAIR Guiding Principles

GO FAIR. *FAIR Principles*.
[Principles overview](https://www.go-fair.org/fair-principles/).

Used as guidance for findable, accessible, interoperable and reusable scientific data
and metadata.

<a id="r9"></a>
### R9 — Nextflow

Nextflow. *Official documentation*.
[Documentation](https://www.nextflow.io/docs/latest/index.html).

Referenced as an established model for portable, reproducible scientific workflows;
it is not declared as a mandatory LABIO runtime.

## Scheduling and observability

<a id="r10"></a>
### R10 — Kueue

Kubernetes SIG Scheduling. *Kueue overview*.
[Official documentation](https://kueue.sigs.k8s.io/docs/overview/).

Referenced for quota, admission, fair sharing and heterogeneous batch workloads in
institutional resource pools.

<a id="r11"></a>
### R11 — OpenTelemetry

Cloud Native Computing Foundation. *OpenTelemetry documentation*.
[Official documentation](https://opentelemetry.io/docs/).

Referenced for vendor-neutral metrics, logs and distributed traces.

<a id="r12"></a>
### R12 — Prometheus

Prometheus Authors and The Linux Foundation. *Prometheus overview*.
[Official documentation](https://prometheus.io/docs/introduction/overview/).

Referenced for time-series monitoring and alerting.

## Compute infrastructure

<a id="r13"></a>
### R13 — NVIDIA A100

NVIDIA. *NVIDIA A100 Tensor Core GPU datasheet*.
[Official datasheet](https://www.nvidia.com/content/dam/en-zz/Solutions/Data-Center/a100/pdf/nvidia-a100-datasheet-nvidia-us-2188504-web.pdf).

Used only to describe accelerator families and the need to record memory, form factor
and precision when benchmarking expected hardware.

<a id="r14"></a>
### R14 — NVIDIA H100

NVIDIA. *NVIDIA H100 Tensor Core GPU*.
[Official product documentation](https://www.nvidia.com/en-us/data-center/h100/).

Used only for future infrastructure planning. No acquisition, model or performance is
claimed by this reference.

## Mobile execution

<a id="r15"></a>
### R15 — Android foreground services

Google Android Developers. *Foreground services overview*.
[Official documentation](https://developer.android.com/develop/background-work/services/fgs).

Used for user-visible, policy-constrained background execution on compatible Android
devices.

## Reference maintenance

References should prefer standards bodies, peer-reviewed primary research and official
vendor documentation. Access dates and version numbers should be added when a technical
decision is frozen into a release or architecture decision record.
