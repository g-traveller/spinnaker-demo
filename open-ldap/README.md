# Add Open Ldap Helm repository:
$ helm repo add stable http://mirror.azure.cn/kubernetes/charts/

# Update your local Helm chart repository cache:
$ helm repo update

# To install Helm chart:
$ helm install openldap stable/openldap --namespace spinnaker -f openldap-values.yaml

# Add the Helm repository:
$ helm repo add cetic https://cetic.github.io/helm-charts

# Update your local Helm chart repository cache:
$ helm repo update

# To install Helm chart:
$ helm install phpldapadmin cetic/phpldapadmin --namespace spinnaker -f phpldapadmin-values.yaml

# Get LDAP admin password
kubectl get secret --namespace spinnaker openldap -o jsonpath="{.data.LDAP_ADMIN_PASSWORD}" | base64 --decode; echo
kubectl get secret --namespace spinnaker openldap -o jsonpath="{.data.LDAP_CONFIG_PASSWORD}" | base64 --decode; echo

# Login
DN: cn=admin,dc=pdcn,dc=com

# LDAP user
spinnakeradmin / 1234567abcd
