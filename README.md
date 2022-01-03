# aws-load-balancer-controller-crds

Install CRDs for [aws-load-balancer-controller helm chart](https://github.com/aws/eks-charts/tree/master/stable/aws-load-balancer-controller)

Aws-load-balancer-controller helm chart does not yet provide a way to install CRDs with the chart.

This means the CRDs have to be installed beforehand.

With terraform this is not really doable because [kubernetes_manifest](https://registry.terraform.io/providers/hashicorp/kubernetes/latest/docs/resources/manifest) is still in beta and requires API access during planning time.

Since Helm3 a best practice seems to have a dedicated chart for CRDs (https://helm.sh/docs/chart_best_practices/custom_resource_definitions/)

## Update

- Copy https://raw.githubusercontent.com/kubernetes-sigs/aws-load-balancer-controller/main/helm/aws-load-balancer-controller/crds/crds.yaml
- `helm package .`
- `helm repo index .`
