# Kubernetes

Part of the `not-a-toy` platform engineering project.

## OpenTelemetry Helm charts

The `platform/argocd/opentelemetry/` resources register the public
`Cliqeu-Lab/opentelemetry-helm-charts` Git repository and define one automated
Argo CD Application for each chart directory. Apply them with
`configuration/apply-argocd-opentelemetry.yaml` after installing Argo CD.
