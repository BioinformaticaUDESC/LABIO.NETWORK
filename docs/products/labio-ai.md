# LABIO AI

**Status:** research and development.

LABIO AI is the planned bioinformatics agent for the LABIO ecosystem. It is intended
to help researchers understand methods, prepare reproducible analyses, select approved
tools and interpret outputs while preserving evidence, uncertainty and user control.

## Architecture direction

```text
research question
       |
       v
intent and permission check
       |
       +----> scientific RAG ----> cited context
       |
       +----> domain-tuned model -> structured proposal
       |
       +----> LABIO tools --------> validated action plan
       v
researcher confirmation
       |
       v
Workspace job submission
```

## Technical boundaries

| Layer | Responsibility | Must not do |
|---|---|---|
| Retrieval | Select versioned passages allowed for the active user and project | Cross project or institutional access boundaries |
| Model | Produce an explanation or structured proposal from the permitted context | Present generated text as verified scientific evidence |
| Tool gateway | Validate typed parameters against an approved application schema | Execute arbitrary model-generated commands |
| Policy | Check identity, data class, credit budget and requested effect | Infer authorization from conversational intent alone |
| Evidence | Attach source, collection version and retrieval metadata | Hide uncertainty or unsupported claims |
| Evaluation | Measure task accuracy, citations, safety and reproducibility | Use a single aggregate score as proof of scientific validity |

## RAG layer

Retrieval-augmented generation should use versioned, attributable collections such as
approved documentation, protocols, public literature metadata, application manuals and
institution-authorized knowledge bases. Each collection requires provenance, access
control, update policy and traceable citations.

The original RAG formulation is cited as the conceptual foundation
([Lewis et al., 2020](../references.md#r7)); production
behavior still requires LABIO-specific evaluation rather than assuming paper results
transfer directly to bioinformatics tasks.

## Fine-tuning layer

Fine-tuning may improve bioinformatics terminology, structured tool use, parameter
formats and common analytical reasoning patterns. It does not replace retrieval of
current evidence and must not silently train on private user data. Training datasets
require documented origin, license, consent, filtering and evaluation.

## Agent boundaries

LABIO AI may draft a workflow or explain a result. Submission that spends credits,
accesses restricted data, changes a project or launches computation requires explicit
authorization and a visible summary of parameters, estimated cost and destination.

## Evaluation

- citation correctness and source coverage;
- bioinformatics task accuracy;
- parameter and schema validity;
- hallucination and uncertainty behavior;
- data-boundary and prompt-injection resistance;
- reproducibility of generated workflows;
- performance across Portuguese, English and Spanish.

The public repository documents model behavior and evaluations, not proprietary
weights, private corpora, user conversations, access tokens or production prompts
containing internal infrastructure details.
