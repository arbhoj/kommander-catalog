## This is a example custom repo for DKP 2.1.1 +

To add this to a project simply create a gitrepository resource as shown below to the given project

```
export PROJECT=customcatalogdemo

kubectl apply -f - <<EOF
apiVersion: source.toolkit.fluxcd.io/v1beta1
kind: GitRepository
metadata:
  name: demo-project-repo
  namespace: ${PROJECT}
  labels:
    kommander.d2iq.io/gitapps-gitrepository-type: catalog
    kommander.d2iq.io/gitrepository-type: catalog
spec:
  interval: 1m0s
  ref:
    branch: master
  timeout: 20s
  url: https://github.com/arbhoj/kommander-catalog.git
EOF

``` 
