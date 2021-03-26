# Magalix Github Action

Identify violations in your IaC files using Magalix Action.

## Usage

```yml
  - uses: magalixcorp/magalix-action@main
    with:
      webhook: ${{ secrets.GUARD_WEBHOOK }}
```

Full example of the workflow

```yml
# .github/workflows/magalix.yml
name: Magalix

on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

jobs:
  magalix:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Magalix
      uses: magalixcorp/magalix-action@main
      with:
        webhook: ${{ secrets.GUARD_WEBHOOK }}
```



## Parameters

| Name            | Description               | Required  | Default         |
| --------------- | ------------------------- | --------- | --------------- |
| `webhook`       | Guard webhook url         |    Yes    |                 |
| `directory`     | Root directory to scan    |    No     | repository root |




## Result Report
![result report](./assets/screenshot-1.png)



## Github Code Scanning

Magalix action supports [Github Code Scanning](https://docs.github.com/en/code-security/secure-coding/about-code-scanning).

![github code scanning](./assets/screenshot-2.png)
