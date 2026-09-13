---
schedule: "every day at 05:00 UTC"
window: "a few minutes; the clones are refreshed from the pipeline cache"
depends_on: []
status: valid
---
# Nightly build

The scheduled run of the wiki workflow of the configuration repository, next to the runs a push or a dispatch triggers: every morning the [build pipeline](../../processes/ingestion/build-pipeline.md) reads the two content repositories at their `main` ref and publishes the site again, so that the freshness entry of the [home](../../screens/pages/home.md) page and the stale-source findings follow the calendar even when nothing was pushed, and so that a dispatch lost for want of a token is caught up within a day.

## Reads

- [Source](../../objects/ingestion/source.md)

## Writes

- [Build](../../objects/ingestion/build.md)
- [Model](../../objects/inference/model.md)
