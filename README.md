# EKS Quickstart App Dev

This repo contains an initial set of cluster components to be installed and
configured by [eksctl](https://eksctl.io) through GitOps.

## Components

- ALB ingress controller -- to easily expose services to the World.
- [Cluster autoscaler](https://github.com/kubernetes/autoscaler/tree/master/cluster-autoscaler) -- to [automatically add/remove nodes](https://aws.amazon.com/premiumsupport/knowledge-center/eks-cluster-autoscaler-setup/) to/from your cluster based on its usage.
- [Prometheus](https://prometheus.io/) (its [Alertmanager](https://prometheus.io/docs/alerting/alertmanager/), its [operator](https://github.com/coreos/prometheus-operator), its [`node-exporter`](https://github.com/prometheus/node_exporter), [`kube-state-metrics`](https://github.com/kubernetes/kube-state-metrics), and [`metrics-server`](https://github.com/kubernetes-incubator/metrics-server)) -- for powerful metrics & alerts.
- [Grafana](https://grafana.com) -- for a rich way to visualize metrics via dashboards you can create, explore, and share.
- [Kubernetes dashboard](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) -- Kubernetes' standard dashboard.
- [Fluentd](https://www.fluentd.org/) & Amazon's [CloudWatch agent](https://aws.amazon.com/cloudwatch/) -- for cluster & containers' [log collection, aggregation & analytics in CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Container-Insights-setup-logs.html).
- [podinfo](https://github.com/stefanprodan/podinfo) --  a toy demo application.

## Pre-requisites

A running EKS cluster with [IAM policies](https://eksctl.io/usage/iam-policies/) for:

- ALB ingress
- auto-scaler
- CloudWatch

[Here](https://github.com/weaveworks/eksctl/blob/master/examples/eks-quickstart-app-dev.yaml) is a sample `ClusterConfig` manifest that shows how to enable these policies.

**N.B.**: policies are configured at node group level.
Therefore, depending on your use-case, you may want to:

- add these policies to all node groups,
- add [node selectors](https://kubernetes.io/docs/concepts/configuration/assign-pod-node/) to the ALB ingress, auto-scaler and CloudWatch pods, so that they are deployed on the nodes configured with these policies.

## Get in touch

[Create an issue](https://github.com/weaveworks/eks-quickstart-app-dev/issues/new), or
login to [Weave Community Slack (#eksctl)][slackchan] ([signup][slackjoin]).

[slackjoin]: https://slack.weave.works/
[slackchan]: https://weave-community.slack.com/messages/eksctl/
