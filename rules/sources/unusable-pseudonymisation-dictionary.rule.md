---
aliases: [W-PRIVACY-DICTIONARY]
severity: warning
---
# Unusable pseudonymisation dictionary

The pseudonymisation dictionary the configuration names is missing, is not valid YAML or does not match its schema. While pseudonymisation is disabled the finding is a warning and the build goes on; when it is enabled the finding is raised as an error, the build fails and every transcript is withheld from the output, because a site built without the dictionary would publish every name as written.

Check `W-PRIVACY-DICTIONARY`, severity warning by default, documented with a before and after example in the [check pages](https://github.com/concordance-wiki/concordance/blob/main/docs/checks/W-PRIVACY-DICTIONARY.md). The severity can be overridden per project or per repository.

## Applies to

- [Source](../../objects/ingestion/source.md)
- [Build](../../processes/ingestion/build-pipeline.md)
