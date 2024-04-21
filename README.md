# kubectl aws-rds-proxy

Start socat with proxy in Kubernetes and forward local port to AWS RDS Cluster or Instance.

## Installation

### Pre-requirements

* Installed [kubectl net-forward](https://github.com/antitree/krew-net-forward)
* Installed [jq](https://jqlang.github.io/jq/)
* Installed and configured AWS Cli

### Using [krew](https://krew.sigs.k8s.io/)

```bash
kubectl krew index add wojtekk https://github.com/wojtekk/krew-index
kubectl krew install net-forward
kubectl krew install wojtekk/aws-rds-proxy
```

### Using Curl

```bash
curl -LO https://github.com/wojtek/aws-rds-proxy/raw/master/kubectl-aws_rds_proxy
chmod +x ./kubectl-aws_rds_proxy
sudo mv ./kubectl-aws_rds_proxy /usr/local/bin/kubectl-aws_rds_proxy
```

## Usage

```bash
Usage:
  kubectl aws-rds-proxy local_port:rds_db_identifier

Options
  --namespace   Kubectl Namespace
  --debug       Print debug information
  --help        Display help
  --version     Print version
```

## Example

```bash
kubectl aws-rds-proxy 33061:my-rds-cluster-name
kubectl aws-rds-proxy 33062:my-rds-instance-name
```
