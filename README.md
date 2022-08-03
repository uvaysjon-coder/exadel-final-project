# Final Exadel Project

﻿Table of contents

1. Introduction
1. Gitlab ci/cd
1. Grafana and Prometheus
1. Logging
1. Introduction.

The project official repo: <https://github.com/laravelio/laravel.io>

File structure:

{image}

Tools: Kubernetes cluster, Helm, Gitlab

2. Gitlab CI/CD

1. Installing gitlab runner

Doc: <https://docs.gitlab.com/runner/install/linux-manually.html>

1. Configure CI/CD variables

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.001.png)

1. Register runner ![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.002.png)
1. Gitlab-ci.yaml file: <https://gitlab.com/exadel1/laravel-image/-/blob/main/.gitlab-ci.yml> 

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.003.png)

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.004.png)






3. Grafana and Prometheus

Install grafana: <https://grafana.com/docs/grafana/latest/setup-grafana/installation/kubernetes/>

Official repo for prometheus: <https://github.com/bibinwilson/kubernetes-prometheus>

kubectl create namespace monitoring

kubectl create -f clusterRole.yaml

kubectl create -f config-map.yaml

kubectl create  -f prometheus-deployment.yaml 

kubectl get deployments --namespace=monitoring

kubectl create -f prometheus-service.yaml --namespace=monitoring

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.005.png)

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.006.png)

3. Logging

For logging it is used LOKI

helm show values grafana/loki-stack > ~/loki-stack-values.yml

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.007.png)

helm install loki grafana/loki-stack -n loki --create-namespace -f ~/loki-stack-values.yml

![](Aspose.Words.c5a0f3e4-36da-414e-a769-29f02e85d8b1.008.png)
