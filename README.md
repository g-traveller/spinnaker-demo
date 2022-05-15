# Download Spinnaker operator
```
$ mkdir -p spinnaker-operator && cd spinnaker-operator
$ bash -c 'curl -L https://github.com/armory/spinnaker-operator/releases/latest/download/manifests.tgz | tar -xz'
```

# Install or update CRDs cluster wide
```
$ kubectl apply -f deploy/crds
```

# Install operator in namespace spinnaker-operator
```
$ kubectl create ns spinnaker-operator
$ kubectl -n spinnaker-operator apply -f deploy/operator/cluster
```

# Update deploy/spinnaker/basic/spinnakerservice.yml to change Spinnaker's persistence bucket

# Install Spinnaker in "spinnaker" namespace
```
$ kubectl create ns spinnaker
$ kubectl -n spinnaker apply -f deploy/spinnaker/basic
```

# Watch the install progress, check out the pods being created too!
```
$ kubectl -n spinnaker get spinsvc spinnaker -w
```

# Get Spinnaker service public URL
```
$ kubectl -n spinnaker get spinsvc spinnaker -w
```

# Get canary content
```
curl -H 'Cache-Control: no-cache, no-store' http://aebb04a1b824a41bcb639f7406f8d9fb-798f487cb79ccf56.elb.cn-north-1.amazonaws.com.cn:8080
```