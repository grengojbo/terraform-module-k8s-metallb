# Terraform module manage kubernetes metallb

[MetalLB](https://metallb.universe.tf/) is a load-balancer implementation for bare metal [Kubernetes](https://kubernetes.io/) clusters, using standard routing protocols.

## Required Valriables

  * Enabled module, metallb_enabled = "true" or "false"
  * Control over IPs from 192.168.1.240 to 192.168.1.250, metallb_ip_range = "192.168.1.240-192.168.1.250"

## Example

```
provider "k8s" {
  # kubeconfig     = "~/.kube/config"
  # kubecontext    = <context within kubeconfig> #optional
}

module "metallb" {
  source = "./modules/metallb"
  enabled = "${var.metallb_enabled}"
  ip_range = "${var.metallb_ip_range}"
}
```
