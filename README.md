# Pick a release from https://github.com/armory/spinnaker-operator/releases (or clone the repo and use the master branch for the latest development work)
$ mkdir -p spinnaker-operator && cd spinnaker-operator
$ bash -c 'curl -L https://github.com/armory/spinnaker-operator/releases/latest/download/manifests.tgz | tar -xz'
 
# Install or update CRDs cluster wide
$ kubectl apply -f deploy/crds/

# Install operator in namespace spinnaker-operator, see below if you want a different namespace
$ kubectl create ns spinnaker-operator
$ kubectl -n spinnaker-operator apply -f deploy/operator/cluster

# Update deploy/spinnaker/basic/spinnakerservice.yml to change Spinnaker's persistence bucket name to a unique name (persistentStorage.s3.bucket value)

# Install Spinnaker in "spinnaker" namespace
$ kubectl create ns spinnaker
$ kubectl -n spinnaker apply -f deploy/spinnaker/basic

# Watch the install progress, check out the pods being created too!
$ kubectl -n spinnaker get spinsvc spinnaker -w

# Get URL
kubectl -n spinnaker get spinsvc spinnaker -w
