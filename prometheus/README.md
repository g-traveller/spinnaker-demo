# Install Promethues in Spinnaker
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

helm install prometheus -n spinnaker -f values.yaml prometheus-community/kube-prometheus-stack