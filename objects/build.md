---
lifecycle: [started, ingested, inferred, checked, written]
---
# Build

One run of the [build pipeline](../processes/build-pipeline.md) on a configuration: the sources it ingested with their commits, the [model](model.md) and the build log it wrote, and its summary. The summary counts the [entities](entity.md) per type, the [links](link.md) per method, the keyword pages published and the expressions under the threshold, the twin [resources](resource.md) reconciled, and the [findings](finding.md) per severity and per check; the log carries the same figures, the contracts imported and every finding. The only dated part of a build is its timestamp, taken from the injected clock, so that two builds on unchanged sources are byte-identical. Next to the model and the log, a build writes one fragment per entity, the rendered note or the passages of a keyword page, and the site itself; `concordance render` rebuilds the site from the model and the fragments without touching a source. A build fails only according to `build.fail_on`, after its model, its log, its fragments and its site are written.
