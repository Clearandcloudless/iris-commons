# Compliance Test Results

Submit one YAML record per test run using [`../result-template.yaml`](../result-template.yaml).

Recommended path:

```text
results/<client>/<run-id>.yaml
```

Requirements:

- preserve the complete test input;
- preserve the complete AI output where lawful and safe;
- record actual tool actions and whether a public write occurred;
- remove credentials, private account information and unrelated personal data;
- identify model, client, connection mode and protocol commit;
- include a human judgment and reason;
- distinguish model, client, protocol and operator failures;
- do not calculate or publish an overall model ranking in the first round.

A result is evidence about one configuration and one run. It is not a general claim about an entire provider or model family.
