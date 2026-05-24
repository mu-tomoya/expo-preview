# My Custom Action

Simple example of a custom GitHub Action implemented as a composite action.

## Inputs

| Name | Required | Default | Description |
| --- | --- | --- | --- |
| `name` | No | `world` | Name to greet |

## Outputs

| Name | Description |
| --- | --- |
| `greeted-name` | The name that was greeted |

## Usage (from another repository)

```yaml
name: Use custom action

on:
  workflow_dispatch:

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: <owner>/<repo>@v1
        with:
          name: Tomoya
```

## Local test in this repository

A workflow is already included:

- `.github/workflows/test-action.yml`

You can run it from the Actions tab with `workflow_dispatch`.

## Release tags

Create tags for stable references:

- `v1`
- `v1.0.0`
