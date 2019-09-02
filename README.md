# EKS Quickstart App Dev

This repo contains an initial set of cluster components to be installed and
configured by [eksctl](https://eksctl.io) through GitOps.

## Components

- ALB ingress controller -- to easily expose services to the World.
- [Cluster autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) -- to [automatically add/remove nodes](https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-autoscaler-setup/) to/from your cluster based on its usage.
- [Helm](https://helm.sh/) -- Kubernetes' package manager.
- [Flux](https://docs.fluxcd.io/en/stable/) and its [Flux-Helm operator](https://github.com/fluxcd/helm-operator-get-started) -- for [GitOps](https://github.com/weaveworks/awesome-gitops), i.e. git-based continuous delivery.
- [Prometheus](https://prometheus.io/) (its [Alertmanager](https://prometheus.io/docs/alerting/alertmanager/), its [operator](https://github.com/coreos/prometheus-operator), its [`node-exporter`](https://github.com/prometheus/node_exporter), [`kube-state-metrics`](https://github.com/kubernetes/kube-state-metrics), and [`metrics-server`](https://github.com/kubernetes-incubator/metrics-server)) -- for powerful metrics & alerts.
- [Grafana](https://grafana.com) -- for a rich way to visualize all metrics via your favourite dashboards.
- [Kubernetes dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) -- Kubernetes' standard dashboard.
- [Fluentd](https://www.fluentd.org/) & Amazon's [CloudWatch agent](https://aws.amazon.com/cloudwatch/) -- for cluster & containers' [log collection, aggregation & analytics in CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Container-Insights-setup-logs.html).
- [podinfo](https://github.com/stefanprodan/podinfo) -- our recommended demo application to discover Kubernetes.

## Get in touch

[Create an issue](https://github.com/weaveworks/eks-quickstart-app-dev/issues/new), or
login to [Weave Community Slack (#eksctl)][slackchan] ([signup][slackjoin]).

[slackjoin]: https://slack.weave.works/
[slackchan]: https://weave-community.slack.com/messages/eksctl/
