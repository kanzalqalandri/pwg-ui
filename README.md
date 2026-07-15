# pwg-ui

App repo for the [GitOps Platform Design v2](https://apportoteam.atlassian.net/wiki/spaces/DevOps/pages/2250047490).

- `helm/` — chart (simple nginx) that ships with the app.
- `.github/workflows/ci.yml` — lints/validates the chart.
- `.github/workflows/deploy-dev.yml`, `list-tenants.yml` — thin callers into the
  DevOps-owned [`platform-workflows`](https://github.com/kanzalqalandri/platform-workflows).

Deploy: **Actions → Deploy**, give a `tenant` + `image_tag`; the platform commits
to `platform-config` and ArgoCD syncs it onto the tenant's cluster.
