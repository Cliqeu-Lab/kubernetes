# Kubernetes

Part of the `not-a-toy` platform engineering project.

## OpenTelemetry Helm charts

The `platform/argocd/opentelemetry/` resources register the public
`Cliqeu-Lab/opentelemetry-helm-charts` Git repository and define one automated
Argo CD Application for each chart directory. Apply them with
`configuration/apply-argocd-opentelemetry.yaml` after installing Argo CD.

## MetalLB

The `platform/argocd/metallb/metallb.yaml` Application combines the upstream
MetalLB Helm chart with the `platform/metallb/` address pool and L2
advertisement. Apply it with `configuration/apply-argocd-metallb.yaml` after
installing Argo CD. Argo CD 2.6 or newer is required for the multi-source
Application.

## Longhorn

The `platform/argocd/longhorn/longhorn.yaml` Application installs the upstream
Longhorn Helm chart into `longhorn-system`. Apply it with
`configuration/apply-argocd-longhorn.yaml` after installing Argo CD.

## cert-manager

The `platform/argocd/cert-manager/cert-manager.yaml` Application installs
cert-manager from the Jetstack Helm repository with CRDs enabled. Apply it
with `configuration/apply-argocd-cert-manager.yaml` after installing Argo CD.

## Kagent agents

`kagent/kagent-agents.yaml` defines a shared Harness and AgentTemplate/Agent
pairs for Kubernetes, Helm, Argo Rollouts, Istio, Cilium, kgateway, and
observability. The templates reference the `gemini-model-config` in
`kagent/kagent-model-config.yaml`. Before applying these resources, ensure the
Kagent CRDs, `kagent` namespace, `kagent-default` worker pool, and
`kagent-tool-server` RemoteMCPServer are available.
