# 37024

Reproduction for Renovate issue https://github.com/renovatebot/renovate/discussions/37024.

Github workflows use in-house github action with non-standard version tags `@<action-name>-v<semver>` e.g.:
```yaml
...
  uses: sequoiahead/renovate-reproduction/build-action@build-action-v1.0.0
...
```

Setup consist of 3 Github repos:
https://github.com/sequoiahead/renovate-reproduction-config - contains renovate configuration

https://github.com/sequoiahead/renovate-reproduction - includes config from `renovate-reproduction-config`. This is 
repository to get update PRs created

https://github.com/sequoiahead/renovate-reproduction-actions - Github Actions repository with tags `@<action-name>-v<semver>` 
representing GHAs version


## Current behavior

Renovate does not suggest update for `build-action` used in `.github/workflows/build.yaml`

## Expected behavior

Renovate suggests update for `build-action` version from `build-action-v1.0.0` to `build-action-v1.2.0` e.g.

```yaml
...
  uses: sequoiahead/renovate-reproduction/build-action@build-action-v1.2.0
...
```

## Link to the Renovate issue or Discussion

Renovate Discussion https://github.com/renovatebot/renovate/discussions/37024.
Renovate log https://developer.mend.io/github/sequoiahead/renovate-reproduction/-/job/01985c2e-3e1c-77fd-8ed8-08256d77c7a7
