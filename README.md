<div align="center">

<h1>LABIO.NETWORK</h1>

<h3>Distributed Bioinformatics Computing Infrastructure</h3>

<p>
A federated scientific computing network connecting institutional infrastructure,
community computers, and mobile devices for bioinformatics and computational biology.
</p>

<p>
<strong>Coordinating Institution:</strong><br>
Universidade do Estado de Santa Catarina — UDESC
</p>

<p>
<strong>Status:</strong> Research • Architecture Design • Prototype Development
</p>

<hr>

<p>
<a href="#overview">Overview</a> •
<a href="#architecture">Architecture</a> •
<a href="#compute-nodes">Compute Nodes</a> •
<a href="#scientific-applications">Applications</a> •
<a href="#scheduling">Scheduling</a> •
<a href="#security">Security</a> •
<a href="#credits">Credits</a> •
<a href="#whitepaper">Whitepaper</a>
</p>

</div>

<hr>

<h2 id="overview">Overview</h2>

<p>
<strong>LABIO.NETWORK</strong> is a distributed scientific computing infrastructure
designed specifically for <strong>bioinformatics, computational biology,
structural biology, molecular modeling, genomics, metagenomics and scientific
artificial intelligence</strong>.
</p>

<p>
The platform is designed to aggregate heterogeneous computing resources distributed
across universities, research laboratories, workstations, personal computers and
compatible mobile devices into a unified scientific execution environment.
</p>

<p>
The central infrastructure hosted by the
<strong>Universidade do Estado de Santa Catarina — UDESC</strong>
acts as the organizational and orchestration layer of the network.
</p>

<p>
Scientific computation itself is not restricted to the UDESC infrastructure.
Workloads may be executed across compatible resources distributed throughout the network.
</p>

<blockquote>
<strong>Centralized coordination. Distributed scientific computing.</strong>
</blockquote>

<hr>

<h2>Mission</h2>

<p>
LABIO.NETWORK aims to make high-performance bioinformatics computing more accessible
by transforming geographically distributed and underutilized computational resources
into a shared scientific infrastructure.
</p>

<p>The project is based on four fundamental ideas:</p>

<ul>
<li>democratize access to scientific computing;</li>
<li>connect academic computing infrastructure;</li>
<li>allow voluntary contribution of idle computational resources;</li>
<li>increase the scale of computational experiments in biological research.</li>
</ul>

<p>
Instead of requiring every researcher or laboratory to maintain dedicated high-performance
computing infrastructure, LABIO.NETWORK provides a common layer capable of discovering,
classifying and allocating available resources.
</p>

<hr>

<h2 id="architecture">Architecture</h2>

<p>
LABIO.NETWORK separates <strong>control</strong> from <strong>execution</strong>.
</p>

<pre>
                         LABIO.NETWORK
                               |
                               |
                    +----------v----------+
                    |                     |
                    |  UDESC CONTROL      |
                    |      PLANE          |
                    |                     |
                    +----------+----------+
                               |
          +--------------------+--------------------+
          |                    |                    |
          |                    |                    |
          v                    v                    v
 +----------------+   +----------------+   +----------------+
 | INSTITUTIONAL  |   |   COMMUNITY    |   |     MOBILE     |
 |     NODES      |   |      NODES     |   |      NODES     |
 +----------------+   +----------------+   +----------------+
 | HPC            |   | Desktop        |   | Android ARM64  |
 | GPU servers    |   | Workstation    |   | Smartphone     |
 | CPU servers    |   | Personal PC    |   | Mobile CPU     |
 | Universities   |   | GPU computers  |   | Edge compute   |
 +-------+--------+   +-------+--------+   +-------+--------+
         |                    |                    |
         +--------------------+--------------------+
                              |
                              v
                     SCIENTIFIC WORKLOADS
                              |
                              v
                  VALIDATION AND PROVENANCE
                              |
                              v
                           RESULTS
</pre>

<hr>

<h2>UDESC Control Plane</h2>

<p>
The UDESC central infrastructure is designed to operate as the
<strong>LABIO.NETWORK Control Plane</strong>.
</p>

<p>
Its role is to maintain the global logical state of the network and coordinate
distributed resources.
</p>

<p>The Control Plane may contain services responsible for:</p>

<ul>
<li>identity and access management;</li>
<li>device authentication;</li>
<li>device registration;</li>
<li>global job scheduling;</li>
<li>scientific workload queues;</li>
<li>application registry;</li>
<li>workflow coordination;</li>
<li>resource accounting;</li>
<li>LABIO Credits;</li>
<li>result validation;</li>
<li>scientific provenance;</li>
<li>monitoring;</li>
<li>logging;</li>
<li>security auditing;</li>
<li>distributed storage coordination.</li>
</ul>

<pre>
                    UDESC CENTRAL INFRASTRUCTURE
                              |
        +---------------------+----------------------+
        |                     |                      |
        v                     v                      v
   Authentication         Job Scheduler        Application Registry
        |                     |                      |
        +---------------------+----------------------+
                              |
                              v
                         Global Queue
                              |
              +---------------+---------------+
              |               |               |
              v               v               v
        Institutional     Community         Mobile
            Nodes           Nodes            Nodes
</pre>

<p>
The UDESC infrastructure therefore coordinates the network without becoming the
exclusive location where scientific computation must occur.
</p>

<hr>

<h2 id="compute-nodes">Compute Node Classes</h2>

<h3>Institutional Nodes</h3>

<p>
Institutional Nodes are computing resources operated by universities,
research centers and laboratories.
</p>

<p>Examples include:</p>

<ul>
<li>HPC clusters;</li>
<li>GPU clusters;</li>
<li>multi-GPU servers;</li>
<li>CPU servers;</li>
<li>institutional workstations;</li>
<li>research computing infrastructure.</li>
</ul>

<p>
These nodes are intended for computationally demanding workloads such as:
</p>

<ul>
<li>molecular dynamics;</li>
<li>large-scale metagenomics;</li>
<li>genome assembly;</li>
<li>large database searches;</li>
<li>GPU workloads;</li>
<li>machine learning;</li>
<li>large scientific workflows.</li>
</ul>

<hr>

<h3>Community Nodes</h3>

<p>
Community Nodes are computers voluntarily connected to LABIO.NETWORK by researchers,
students, institutions or members of the scientific community.
</p>

<p>Examples include:</p>

<ul>
<li>personal desktops;</li>
<li>research workstations;</li>
<li>gaming GPUs;</li>
<li>laboratory computers;</li>
<li>idle servers;</li>
<li>mini PCs.</li>
</ul>

<p>
Users maintain control over how much of their hardware can be used.
</p>

<pre>
LABIO Compute

Device: Research-Workstation-01

CPU                 32 cores
RAM                 128 GB
GPU                 RTX-class GPU

Contribution policy

CPU                 50%
RAM                 32 GB
GPU                 Enabled
Idle only           Yes
Maximum temperature Configurable
Schedule            Configurable
</pre>

<hr>

<h3>Mobile Nodes</h3>

<p>
Compatible smartphones may participate as <strong>Mobile Nodes</strong>.
</p>

<p>
The initial technical focus is Android devices using 64-bit ARM architectures.
</p>

<p>
Mobile nodes are not intended to execute every bioinformatics application.
Instead, the scheduler assigns only workloads compatible with the device's
architecture, memory, thermal conditions, battery state and expected runtime.
</p>

<p>Potential mobile workloads include:</p>

<ul>
<li>sequence parsing;</li>
<li>small independent docking tasks;</li>
<li>k-mer operations;</li>
<li>small alignment tasks;</li>
<li>statistical calculations;</li>
<li>scoring functions;</li>
<li>parameter sweeps;</li>
<li>data transformations;</li>
<li>result validation;</li>
<li>small portable scientific kernels.</li>
</ul>

<hr>

<h2>LABIO Compute Agent</h2>

<p>
Computers participating in LABIO.NETWORK run a software component called the
<strong>LABIO Compute Agent</strong>.
</p>

<p>
The agent is responsible for communicating with the Control Plane and reporting
the resources that the user has authorized for scientific computing.
</p>

<pre>
User installs LABIO Compute
          |
          v
     Creates account
          |
          v
    Registers device
          |
          v
Authorizes CPU / RAM / GPU
          |
          v
   LABIO Agent starts
          |
          v
Authenticated connection
          |
          v
LABIO.NETWORK Control Plane
          |
          v
Compatible workload assigned
          |
          v
Local isolated execution
          |
          v
Result returned
          |
          v
Validation
          |
          v
LABIO Credits
</pre>

<p>
The distributed node should request work from LABIO.NETWORK instead of requiring
the Control Plane to establish unsolicited inbound connections to personal devices.
</p>

<p>
This model is suitable for systems operating behind:
</p>

<ul>
<li>NAT;</li>
<li>CGNAT;</li>
<li>institutional firewalls;</li>
<li>residential routers;</li>
<li>dynamic IP addresses;</li>
<li>mobile networks.</li>
</ul>

<hr>

<h2 id="scientific-applications">Scientific Applications</h2>

<p>
LABIO.NETWORK is being designed to support different categories of applications
used in modern computational biology.
</p>

<table>
<thead>
<tr>
<th align="left">Scientific Area</th>
<th align="left">Examples of Workloads</th>
</tr>
</thead>

<tbody>

<tr>
<td>Structural Bioinformatics</td>
<td>Molecular docking, structural analysis, scoring</td>
</tr>

<tr>
<td>Molecular Dynamics</td>
<td>GROMACS and related simulation workflows</td>
</tr>

<tr>
<td>Genomics</td>
<td>Alignment, assembly, annotation and variant analysis</td>
</tr>

<tr>
<td>Metagenomics</td>
<td>Classification, assembly and functional analysis</td>
</tr>

<tr>
<td>Phylogenetics</td>
<td>Tree inference, evolutionary models and sequence analysis</td>
</tr>

<tr>
<td>Sequence Analysis</td>
<td>BLAST-like searches, k-mer analysis and transformations</td>
</tr>

<tr>
<td>Scientific AI</td>
<td>Inference and selected machine-learning workloads</td>
</tr>

<tr>
<td>Scientific Workflows</td>
<td>Multi-stage computational pipelines</td>
</tr>

</tbody>
</table>

<hr>

<h2>Application Registry</h2>

<p>
Not every scientific application can run on every device.
</p>

<p>
For this reason, LABIO.NETWORK uses the concept of a
<strong>LABIO Application Registry</strong>.
</p>

<p>
Each scientific application may provide different execution artifacts according to
operating system, architecture and runtime.
</p>

<pre>
                       AutoDock Vina
                             |
             +---------------+---------------+
             |               |               |
             v               v               v
        Linux AMD64     Linux ARM64     Android ARM64
             |               |               |
             v               v               v
          OCI Image       OCI Image      Native Build
</pre>

<p>
The researcher requests the scientific application.
The scheduler selects the correct implementation automatically.
</p>

<p>
A conceptual application definition may contain:
</p>

<pre>
application:
  name: scientific-application
  version: x.y.z

targets:

  linux-amd64:
    runtime: OCI

  linux-arm64:
    runtime: OCI

  android-arm64:
    runtime: native

requirements:
  cpu: defined
  memory: defined
  gpu: optional

mobile:
  supported: true | false
</pre>

<hr>

<h2>Execution Runtimes</h2>

<p>
LABIO.NETWORK is not designed around the assumption that a single runtime will work
on every platform.
</p>

<p>The architecture may support multiple execution models:</p>

<table>
<thead>

<tr>
<th align="left">Runtime</th>
<th align="left">Primary Use</th>
</tr>

</thead>

<tbody>

<tr>
<td>OCI Containers</td>
<td>Linux servers, clusters, workstations and institutional nodes</td>
</tr>

<tr>
<td>Native Applications</td>
<td>Android ARM64 and platform-specific optimized workloads</td>
</tr>

<tr>
<td>Portable Runtime / WASM</td>
<td>Selected cross-platform computational kernels</td>
</tr>

</tbody>
</table>

<pre>
                        SCIENTIFIC JOB
                              |
                              v
                       LABIO SCHEDULER
                              |
          +-------------------+-------------------+
          |                   |                   |
          v                   v                   v
      OCI Container        Native             Portable
          |                   |                   |
          v                   v                   v
   Server / Desktop        Android          Multi-platform
</pre>

<hr>

<h2 id="scheduling">Global Scheduling</h2>

<p>
The <strong>LABIO Global Scheduler</strong> determines where each workload should run.
</p>

<p>
Scheduling decisions may consider:
</p>

<ul>
<li>operating system;</li>
<li>processor architecture;</li>
<li>available CPU cores;</li>
<li>available RAM;</li>
<li>GPU vendor;</li>
<li>GPU model;</li>
<li>GPU memory;</li>
<li>CUDA or other accelerator requirements;</li>
<li>application compatibility;</li>
<li>node reliability;</li>
<li>node availability;</li>
<li>network bandwidth;</li>
<li>data locality;</li>
<li>energy policies;</li>
<li>expected runtime;</li>
<li>job priority;</li>
<li>institutional policy;</li>
<li>scientific data classification.</li>
</ul>

<p>
A generic candidate score may be expressed conceptually as:
</p>

<p align="center">
<strong>
S<sub>node</sub> =
w<sub>c</sub>C +
w<sub>r</sub>R +
w<sub>a</sub>A +
w<sub>p</sub>P +
w<sub>n</sub>N +
w<sub>l</sub>L -
w<sub>e</sub>E
</strong>
</p>

<p>where:</p>

<ul>
<li><strong>C</strong> = hardware and runtime compatibility;</li>
<li><strong>R</strong> = node reliability;</li>
<li><strong>A</strong> = resource availability;</li>
<li><strong>P</strong> = expected scientific performance;</li>
<li><strong>N</strong> = network quality;</li>
<li><strong>L</strong> = data locality;</li>
<li><strong>E</strong> = estimated execution cost or resource penalty;</li>
<li><strong>w</strong> = configurable scheduler weights.</li>
</ul>

<hr>

<h2>Heterogeneous Computing</h2>

<p>
LABIO.NETWORK is designed for heterogeneous computing environments.
</p>

<table>

<thead>

<tr>
<th align="left">Node</th>
<th align="left">Architecture</th>
<th align="left">Typical Capability</th>
</tr>

</thead>

<tbody>

<tr>
<td>Mobile Device</td>
<td>ARM64</td>
<td>Small CPU workloads</td>
</tr>

<tr>
<td>Desktop</td>
<td>x86-64</td>
<td>CPU workloads</td>
</tr>

<tr>
<td>GPU Workstation</td>
<td>x86-64 + GPU</td>
<td>Accelerated scientific workloads</td>
</tr>

<tr>
<td>Institutional Server</td>
<td>x86-64 / ARM64</td>
<td>Large CPU or memory workloads</td>
</tr>

<tr>
<td>GPU Cluster</td>
<td>Multi-GPU</td>
<td>Large accelerated workloads</td>
</tr>

</tbody>

</table>

<hr>

<h2>Compute Capacity</h2>

<p>
The theoretical floating-point capacity of a distributed network can be represented by:
</p>

<p align="center">
<strong>
P<sub>peak</sub> = Σ P<sub>i</sub>
</strong>
</p>

<p>
where <strong>P<sub>i</sub></strong> represents the peak floating-point performance
of each participating device.
</p>

<p>
However, theoretical TFLOPS alone do not represent real scientific productivity.
</p>

<p>
The effective capacity depends on factors including:
</p>

<ul>
<li>device availability;</li>
<li>software efficiency;</li>
<li>architecture compatibility;</li>
<li>communication overhead;</li>
<li>scheduler efficiency;</li>
<li>memory limitations;</li>
<li>application characteristics.</li>
</ul>

<p>
A simplified effective-capacity model can therefore be written as:
</p>

<p align="center">
<strong>
P<sub>effective</sub> =
Σ
P<sub>i</sub>
×
A<sub>i</sub>
×
E<sub>i</sub>
×
C<sub>i</sub>
</strong>
</p>

<p>where:</p>

<ul>
<li><strong>P<sub>i</sub></strong> = theoretical performance;</li>
<li><strong>A<sub>i</sub></strong> = availability factor;</li>
<li><strong>E<sub>i</sub></strong> = execution efficiency;</li>
<li><strong>C<sub>i</sub></strong> = workload compatibility factor.</li>
</ul>

<hr>

<h2>Scientific Benchmarking</h2>

<p>
LABIO.NETWORK will not evaluate its infrastructure only through generic TFLOPS.
</p>

<p>
The project proposes a workload-oriented benchmarking system:
<strong>LABIO Scientific Benchmark Suite</strong>.
</p>

<p>Examples of useful scientific metrics include:</p>

<ul>
<li>dockings per hour;</li>
<li>ligands screened per day;</li>
<li>GROMACS nanoseconds per day;</li>
<li>reads processed per second;</li>
<li>sequences aligned per second;</li>
<li>assemblies completed per day;</li>
<li>inference operations per second;</li>
<li>workflow completion time.</li>
</ul>

<p>
This allows the scheduler to select resources according to actual scientific performance
instead of relying exclusively on theoretical hardware specifications.
</p>

<hr>

<h2>Network Effect</h2>

<p>
The scientific potential of LABIO.NETWORK increases as more compatible devices
join the infrastructure.
</p>

<p>
For independent workloads, the available parallelism can increase approximately
with the number of available nodes until another resource becomes the limiting factor.
</p>

<p>
For a workload containing <strong>N</strong> independent tasks with an average
execution time <strong>t</strong>, executed across <strong>D</strong> equivalent
available devices, an idealized completion time can be approximated by:
</p>

<p align="center">
<strong>
T ≈ (N × t) / D
</strong>
</p>

<p>
Real execution time also includes scheduling, communication, validation and
heterogeneity overhead.
</p>

<hr>

<h2>Drug Discovery and Virtual Screening</h2>

<p>
One important application area for distributed computing is
<strong>large-scale virtual screening</strong>.
</p>

<p>
Docking workloads are especially interesting because many ligand-target evaluations
can be processed independently.
</p>

<pre>
                   Virtual Screening Campaign

                       Target Protein
                             |
                             v
                     Ligand Library
                             |
         +-------------------+-------------------+
         |                   |                   |
         v                   v                   v
      Ligand 1            Ligand 2            Ligand N
         |                   |                   |
         v                   v                   v
       Node A              Node B              Node N
         |                   |                   |
         +-------------------+-------------------+
                             |
                             v
                       Ranked Results
</pre>

<p>
As computational capacity grows, researchers may evaluate larger combinations of:
</p>

<ul>
<li>ligands;</li>
<li>protein targets;</li>
<li>protein conformations;</li>
<li>docking replicas;</li>
<li>binding-site configurations;</li>
<li>parameter combinations;</li>
<li>candidate compounds.</li>
</ul>

<p>
The potential throughput of a docking network may be represented as:
</p>

<p align="center">
<strong>
D<sub>day</sub> =
Σ
(86,400 × A<sub>i</sub>) / t<sub>i</sub>
</strong>
</p>

<p>where:</p>

<ul>
<li><strong>D<sub>day</sub></strong> = estimated validated docking tasks per day;</li>
<li><strong>A<sub>i</sub></strong> = availability of node <em>i</em>;</li>
<li><strong>t<sub>i</sub></strong> = benchmarked time per docking task on node <em>i</em>.</li>
</ul>

<p>
Actual scientific throughput must always be obtained from validated benchmarks,
not inferred directly from GPU TFLOPS.
</p>

<hr>

<h2>Scientific Workflows</h2>

<p>
Bioinformatics analyses frequently consist of multiple dependent computational stages.
</p>

<pre>
FASTQ
  |
  v
Quality Control
  |
  v
Host Removal
  |
  v
Classification
  |
  v
Assembly
  |
  v
Annotation
  |
  v
Statistical Analysis
</pre>

<p>
LABIO.NETWORK is being designed to integrate workflow-management systems such as
<strong>Nextflow</strong>.
</p>

<p>
The workflow engine defines dependencies between scientific processes,
while LABIO.NETWORK determines where compatible tasks should execute.
</p>

<pre>
                    SCIENTIFIC WORKFLOW
                            |
                     Workflow Engine
                            |
            +---------------+---------------+
            |               |               |
            v               v               v
         Process A       Process B       Process C
            |               |               |
            +---------------+---------------+
                            |
                            v
                    LABIO SCHEDULER
                            |
          +-----------------+-----------------+
          |                 |                 |
          v                 v                 v
    Institutional       Community           Mobile
</pre>

<hr>

<h2 id="security">Security Architecture</h2>

<p>
Security is a fundamental requirement because scientific workloads may execute
on infrastructure that does not belong to the researcher submitting the analysis.
</p>

<p>
The architecture therefore follows a
<strong>Zero Trust-oriented security model</strong>.
</p>

<p>The core security principle is:</p>

<pre>
USER != DEVICE
DEVICE != APPLICATION
APPLICATION != DATA
DATA != HOST FILESYSTEM
</pre>

<p>
Authorization in one domain must not automatically grant unrestricted access to another.
</p>

<hr>

<h3>Security Principles</h3>

<ul>
<li>Zero Trust;</li>
<li>least privilege;</li>
<li>authenticated devices;</li>
<li>short-lived credentials;</li>
<li>encrypted transport;</li>
<li>workload isolation;</li>
<li>signed applications;</li>
<li>cryptographic artifact hashes;</li>
<li>application allowlists;</li>
<li>result validation;</li>
<li>audit logging;</li>
<li>scientific provenance;</li>
<li>resource limits;</li>
<li>network isolation;</li>
<li>reproducible environments.</li>
</ul>

<hr>

<h3>Threat Model</h3>

<p>
The architecture must assume the possible existence of:
</p>

<ul>
<li>malicious compute nodes;</li>
<li>compromised user accounts;</li>
<li>tampered applications;</li>
<li>fraudulent computational results;</li>
<li>Sybil attacks;</li>
<li>replay attacks;</li>
<li>credential theft;</li>
<li>data exfiltration attempts;</li>
<li>malicious workload submissions;</li>
<li>software supply-chain attacks;</li>
<li>denial-of-service attempts.</li>
</ul>

<hr>

<h3>Application Security</h3>

<p>
Researchers must not be allowed to directly distribute arbitrary executable files
to volunteer machines.
</p>

<p>The intended application lifecycle is:</p>

<pre>
Application Source
       |
       v
LABIO Build System
       |
       v
Dependency Validation
       |
       v
Security Analysis
       |
       v
Compatibility Tests
       |
       v
Scientific Benchmark
       |
       v
Cryptographic Signature
       |
       v
LABIO Application Registry
       |
       v
Approved Execution
</pre>

<p>
Nodes execute only approved applications that can be validated against the registry.
</p>

<hr>

<h3>Workload Isolation</h3>

<p>A scientific job should see only the resources explicitly assigned to it.</p>

<pre>
+-----------------------------------+
|       LABIO EXECUTION SANDBOX     |
|                                   |
| Scientific Application            |
| Input Files                       |
| Temporary Working Directory       |
| Assigned CPU                      |
| Assigned RAM                      |
| Assigned GPU                      |
|                                   |
+-----------------------------------+

NO ACCESS TO:

User documents
Personal photos
Browser data
SSH keys
Passwords
Unrelated host files
Other scientific jobs
</pre>

<hr>

<h2>Scientific Data Classification</h2>

<p>
Not all biological datasets should be sent to volunteer infrastructure.
</p>

<p>
LABIO.NETWORK therefore proposes data classification before scheduling.
</p>

<table>

<thead>

<tr>
<th align="left">Class</th>
<th align="left">Description</th>
<th align="left">Execution Policy</th>
</tr>

</thead>

<tbody>

<tr>
<td>T0</td>
<td>Public scientific data</td>
<td>Eligible for distributed execution</td>
</tr>

<tr>
<td>T1</td>
<td>Internal non-sensitive research data</td>
<td>Policy-controlled execution</td>
</tr>

<tr>
<td>T2</td>
<td>Restricted research data</td>
<td>Trusted institutional nodes</td>
</tr>

<tr>
<td>T3</td>
<td>Sensitive or regulated human data</td>
<td>Controlled infrastructure only</td>
</tr>

</tbody>

</table>

<p>
Sensitive genetic, clinical or identifiable human data should not be distributed
to arbitrary community devices.
</p>

<hr>

<h2>Result Validation</h2>

<p>
Nodes participating in a distributed infrastructure cannot automatically be assumed
to return correct results.
</p>

<p>
LABIO.NETWORK may use application-specific validation, redundancy and trust scoring.
</p>

<pre>
                 Scientific Task
                       |
             +---------+---------+
             |                   |
             v                   v
          Node A               Node B
             |                   |
             v                   v
          Result X             Result X
             |                   |
             +---------+---------+
                       |
                       v
                    VALID
</pre>

<p>For conflicting results:</p>

<pre>
Node A -> Result X
Node B -> Result Y

        Conflict
           |
           v
         Node C
           |
           v
        Result X

A -> Accepted
B -> Rejected / Investigated
C -> Accepted
</pre>

<p>
Redundant execution does not need to be applied uniformly to all jobs.
The validation strategy can depend on node trust, application criticality and
scientific requirements.
</p>

<hr>

<h2>LABIO Node Score</h2>

<p>
Each node may receive an operational trust and performance score.
</p>

<p>A conceptual model is:</p>

<p align="center">
<strong>
S =
αR +
βV +
γA +
δP +
εN
</strong>
</p>

<p>where:</p>

<ul>
<li><strong>R</strong> = reliability;</li>
<li><strong>V</strong> = validated result rate;</li>
<li><strong>A</strong> = availability;</li>
<li><strong>P</strong> = scientific benchmark performance;</li>
<li><strong>N</strong> = network stability.</li>
</ul>

<p>
The score may influence the type and importance of workloads assigned to each node.
</p>

<hr>

<h2 id="credits">LABIO Credits</h2>

<p>
LABIO.NETWORK proposes an internal computational accounting mechanism called
<strong>LABIO Credits</strong>.
</p>

<p>
Credits are intended to represent <strong>validated useful scientific contribution</strong>,
not simple device uptime.
</p>

<p>
The first implementation is intended as an internal scientific resource-accounting system,
not a cryptocurrency.
</p>

<hr>

<h3>Earning Credits</h3>

<p>
A conceptual credit calculation may use:
</p>

<p align="center">
<strong>
C<sub>earned</sub> =
W × R × V × Q
</strong>
</p>

<p>where:</p>

<ul>
<li><strong>W</strong> = normalized computational work completed;</li>
<li><strong>R</strong> = resource factor;</li>
<li><strong>V</strong> = validation factor;</li>
<li><strong>Q</strong> = quality/reliability factor.</li>
</ul>

<p>
A node does not receive full credit simply for remaining online.
The system rewards successfully completed and validated scientific computation.
</p>

<hr>

<h3>Using Credits</h3>

<p>
Credits may be consumed when a researcher uses distributed computational capacity.
</p>

<p>A conceptual cost model can be expressed as:</p>

<p align="center">
<strong>
C<sub>job</sub> =
CPU +
GPU +
Memory +
Storage +
Transfer +
Priority
</strong>
</p>

<p>
Each component may be normalized into a common internal accounting unit.
</p>

<hr>

<h3>Community Reciprocity</h3>

<p>The basic economic principle is:</p>

<blockquote>
<strong>Contribute computational resources to science and receive computational capacity in return.</strong>
</blockquote>

<pre>
                 COMMUNITY MEMBER

                      contributes
                     CPU / GPU time
                          |
                          v
                    LABIO.NETWORK
                          |
                          v
                     VALIDATED WORK
                          |
                          v
                     LABIO CREDITS
                          |
                          v
                    COMPUTE ACCESS
</pre>

<hr>

<h2>Community Benefits</h2>

<p>
Community participation creates value at multiple levels.
</p>

<ul>
<li>access to distributed computational resources;</li>
<li>LABIO Credits;</li>
<li>scientific contribution records;</li>
<li>node contribution statistics;</li>
<li>institutional participation metrics;</li>
<li>potential contributor recognition;</li>
<li>community computing rankings;</li>
<li>scientific infrastructure sharing;</li>
<li>greater access to computational biology.</li>
</ul>

<hr>

<h2>Institutional Resource Pools</h2>

<p>
Universities may contribute infrastructure while maintaining institutional control
over resource allocation.
</p>

<p>Examples of policies include:</p>

<ul>
<li>institution-first scheduling;</li>
<li>reserved quotas;</li>
<li>shared idle capacity;</li>
<li>inter-institutional resource exchange;</li>
<li>project-specific resource pools;</li>
<li>priority scheduling for approved scientific programs.</li>
</ul>

<pre>
                    LABIO.NETWORK
                          |
          +---------------+---------------+
          |                               |
          v                               v
    UNIVERSITY A                     UNIVERSITY B
          |                               |
   contributes GPUs                 contributes CPUs
          |                               |
          +---------------+---------------+
                          |
                          v
                 SHARED SCIENTIFIC POOL
</pre>

<hr>

<h2>Scientific Provenance</h2>

<p>
Every scientific job should generate a provenance record containing information such as:
</p>

<ul>
<li>job identifier;</li>
<li>application name;</li>
<li>application version;</li>
<li>application artifact hash;</li>
<li>input file hashes;</li>
<li>execution parameters;</li>
<li>runtime;</li>
<li>architecture;</li>
<li>node class;</li>
<li>submission timestamp;</li>
<li>execution timestamp;</li>
<li>completion timestamp;</li>
<li>validation state.</li>
</ul>

<pre>
job_id: LAB-XXXXXXXX

application:
  name: scientific-application
  version: x.y.z
  artifact_digest: sha256:...

input:
  file:
    sha256: ...

execution:
  node_class: institutional | community | mobile
  architecture: amd64 | arm64
  runtime: OCI | native | portable

result:
  validated: true
</pre>

<hr>

<h2>Fault Tolerance</h2>

<p>
Community and mobile devices are inherently intermittent.
</p>

<p>A node may:</p>

<ul>
<li>disconnect;</li>
<li>lose network access;</li>
<li>shut down;</li>
<li>become thermally constrained;</li>
<li>become unavailable to LABIO;</li>
<li>be actively used by its owner.</li>
</ul>

<p>
LABIO.NETWORK must therefore treat node failure as a normal operating condition.
</p>

<pre>
AVAILABLE
    |
    v
RESERVED
    |
    v
RUNNING
    |
    +-------------------------+
    |                         |
    v                         v
COMPLETED                  NODE LOST
                              |
                    +---------+---------+
                    |                   |
                    v                   v
              CHECKPOINT            REQUEUE
                    |
                    v
                  RESUME
</pre>

<hr>

<h2>Monitoring and Observability</h2>

<p>The network should monitor metrics including:</p>

<ul>
<li>online nodes;</li>
<li>available CPU cores;</li>
<li>available GPU resources;</li>
<li>available memory;</li>
<li>jobs queued;</li>
<li>jobs running;</li>
<li>jobs completed;</li>
<li>failed jobs;</li>
<li>validation failures;</li>
<li>network throughput;</li>
<li>scheduler latency;</li>
<li>scientific throughput;</li>
<li>resource utilization;</li>
<li>contributed compute time;</li>
<li>credits generated and consumed.</li>
</ul>

<hr>

<h2>High Availability</h2>

<p>
Although UDESC coordinates the Control Plane, the production architecture should
not depend on a single physical server.
</p>

<pre>
                       labio.network
                             |
                             v
                       Load Balancer
                             |
             +---------------+---------------+
             |               |               |
             v               v               v
         Control A       Control B       Control C
             |               |               |
             +---------------+---------------+
                             |
                             v
                      Replicated State
</pre>

<p>
Critical services should progressively support replication and recovery mechanisms.
</p>

<hr>

<h2>Technology Direction</h2>

<p>
The current architecture is evaluating or considering technologies from several
distributed-computing ecosystems.
</p>

<table>

<thead>

<tr>
<th align="left">Layer</th>
<th align="left">Technology Direction</th>
</tr>

</thead>

<tbody>

<tr>
<td>Frontend</td>
<td>React / Next.js</td>
</tr>

<tr>
<td>Control API</td>
<td>Go and/or FastAPI-based services</td>
</tr>

<tr>
<td>Metadata</td>
<td>PostgreSQL</td>
</tr>

<tr>
<td>Institutional Orchestration</td>
<td>Kubernetes</td>
</tr>

<tr>
<td>Batch Queueing</td>
<td>Kueue</td>
</tr>

<tr>
<td>Scientific Workflows</td>
<td>Nextflow</td>
</tr>

<tr>
<td>Containers</td>
<td>OCI-compatible runtimes</td>
</tr>

<tr>
<td>Community Computing</td>
<td>LABIO Compute Agent / volunteer-computing concepts</td>
</tr>

<tr>
<td>Mobile Computing</td>
<td>LABIO Mobile Agent</td>
</tr>

<tr>
<td>Observability</td>
<td>Prometheus-compatible metrics and centralized logging</td>
</tr>

<tr>
<td>Object Storage</td>
<td>S3-compatible infrastructure</td>
</tr>

</tbody>

</table>

<p>
The final selection of technologies will be based on prototype validation,
security analysis, benchmarking and operational requirements.
</p>

<hr>

<h2>Repository Structure</h2>

<pre>
LABIO.NETWORK/

README.md

docs/
  whitepaper/
    LABIO_NETWORK_Technical_Whitepaper_v0.2.docx

architecture/

orchestrator/

agents/
  desktop/
  mobile/

frontend/

benchmarks/

security/

workflows/
</pre>

<hr>

<h2 id="whitepaper">Technical Whitepaper</h2>

<p>
The LABIO.NETWORK technical architecture is described in greater detail in the
project whitepaper.
</p>

<p>
<strong>Current version:</strong> Technical Whitepaper v0.2
</p>

<p>
<a href="docs/whitepaper/LABIO_NETWORK_Technical_Whitepaper_v0.2.docx">
Download the LABIO.NETWORK Technical Whitepaper
</a>
</p>

<hr>

<h2>Development Roadmap</h2>

<h3>Architecture and Prototype</h3>

<ul>
<li>Control Plane specification</li>
<li>device model</li>
<li>job model</li>
<li>Application Registry</li>
<li>scheduler prototype</li>
<li>desktop agent prototype</li>
<li>scientific benchmarking framework</li>
</ul>

<h3>Distributed Execution</h3>

<ul>
<li>Linux compute agent</li>
<li>Windows compute agent</li>
<li>institutional Kubernetes integration</li>
<li>job validation</li>
<li>resource accounting</li>
<li>LABIO Credits prototype</li>
</ul>

<h3>Mobile Computing</h3>

<ul>
<li>Android ARM64 agent</li>
<li>battery-aware scheduling</li>
<li>thermal-aware scheduling</li>
<li>mobile scientific benchmarks</li>
<li>approved ARM64 application registry</li>
</ul>

<h3>Federation</h3>

<ul>
<li>multi-university resource federation</li>
<li>institutional quotas</li>
<li>distributed resource pools</li>
<li>high-availability Control Plane</li>
<li>federated execution policies</li>
</ul>

<h3>Scientific Platform</h3>

<ul>
<li>Jupyter workspace</li>
<li>scientific application catalog</li>
<li>workflow execution</li>
<li>LABIO Chat integration</li>
<li>distributed genomics workflows</li>
<li>distributed structural-biology workflows</li>
<li>large-scale virtual screening</li>
</ul>

<hr>

<h2>Research Questions</h2>

<p>
LABIO.NETWORK is also a distributed-systems research project.
</p>

<p>Questions under investigation include:</p>

<ul>
<li>How should heterogeneous scientific resources be ranked?</li>
<li>How can useful scientific work be measured fairly?</li>
<li>How should credits be normalized across CPU, GPU and mobile devices?</li>
<li>How can fraudulent computation be detected efficiently?</li>
<li>How much redundant execution is necessary for untrusted nodes?</li>
<li>How should scientific workloads be partitioned across heterogeneous architectures?</li>
<li>How can sensitive biological datasets be isolated from community infrastructure?</li>
<li>How should scheduling balance performance, fairness, energy and reliability?</li>
<li>How can mobile computing contribute efficiently without degrading battery lifetime?</li>
<li>How does network scale affect virtual-screening throughput?</li>
<li>How can institutions contribute infrastructure while retaining governance over their resources?</li>
</ul>

<hr>

<h2>Scientific Vision</h2>

<p>
The long-term objective of LABIO.NETWORK is not simply to create a larger computer cluster.
</p>

<p>
The project aims to create a <strong>distributed scientific computing layer</strong>
capable of converting heterogeneous resources into accessible bioinformatics infrastructure.
</p>

<pre>
1 researcher
      +
1 university
      +
1 workstation
      +
1 mobile device
      |
      v
   resources

10 universities
      +
1,000 computers
      +
5,000 mobile devices
      |
      v
 distributed scientific capacity

100+ institutions
      +
large community participation
      |
      v
 federated bioinformatics infrastructure
</pre>

<p>
As the number and diversity of participating resources increase, the network can support
larger parameter spaces, larger ligand libraries, more replicas, more biological targets,
larger genomic datasets and more computational experiments.
</p>

<blockquote>
<strong>
More available compute does not replace scientific rigor.
It expands the number of scientifically justified hypotheses that can be computationally evaluated.
</strong>
</blockquote>

<hr>

<h2>Governance</h2>

<p>
LABIO.NETWORK is designed as an academic and scientific infrastructure.
</p>

<p>
The <strong>Universidade do Estado de Santa Catarina — UDESC</strong>
acts as the coordinating institution of the initial network architecture and
central Control Plane.
</p>

<p>
The architecture is intended to evolve toward institutional federation while preserving:
</p>

<ul>
<li>scientific governance;</li>
<li>security;</li>
<li>reproducibility;</li>
<li>transparent resource accounting;</li>
<li>institutional autonomy;</li>
<li>auditability.</li>
</ul>

<hr>

<h2>Current Status</h2>

<p>
LABIO.NETWORK is currently under:
</p>

<ul>
<li>architectural design;</li>
<li>technical documentation;</li>
<li>prototype development;</li>
<li>distributed-computing evaluation;</li>
<li>security-model development;</li>
<li>scientific workload benchmarking.</li>
</ul>

<p>
Specifications contained in this repository are expected to evolve as the
architecture is experimentally validated.
</p>

<hr>

<h2>Contributing</h2>

<p>
Contribution guidelines will be published as individual components of
LABIO.NETWORK become available for public development.
</p>

<p>Future contribution areas may include:</p>

<ul>
<li>distributed systems;</li>
<li>bioinformatics;</li>
<li>scientific software packaging;</li>
<li>Android ARM64 computing;</li>
<li>container engineering;</li>
<li>workflow development;</li>
<li>cybersecurity;</li>
<li>benchmark development;</li>
<li>scientific validation;</li>
<li>frontend development.</li>
</ul>

<hr>

<h2>Disclaimer</h2>

<p>
LABIO.NETWORK is under active research and development.
</p>

<p>
Architecture descriptions, performance models, resource-accounting mechanisms,
software choices and distributed execution policies described in this repository
represent the current technical design and may change following experimental
validation, security analysis and benchmarking.
</p>

<p>
Illustrative performance equations and scaling models must not be interpreted as
guaranteed scientific throughput.
</p>

<hr>

<div align="center">

<h2>LABIO.NETWORK</h2>

<p>
<strong>Distributed computing for bioinformatics and computational biology.</strong>
</p>

<p>
Coordinated by<br>
<strong>Universidade do Estado de Santa Catarina — UDESC</strong>
</p>

<p>
Brazil
</p>

</div>
