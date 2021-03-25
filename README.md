# Magalix IaC Scanner

## Usage

```yml
    uses: magalixcorp/magalix-action@dev
    with:
        webhook: ${{ secrets.GUARD_WEBHOOK }}
```


## Parameters

| Name            | Description               | Required  | Default         |
| --------------- | ------------------------- | --------- | --------------- |
| `webhook`       | Guard webhook url         | Yes       |                 |
| `directory`     | Root directory to scan    | No        | repository root |



## Full Example


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
      uses: magalixcorp/magalix-action@dev
      with:
        webhook: ${{ secrets.GUARD_WEBHOOK }}
```