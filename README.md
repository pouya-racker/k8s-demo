# k8s-demo

## Useful commands/tools

`kubectl run -it --rm --restart=Never curl --image=curlimages/curl -- curl SERVICE_NAME`

`kubectl run -it --rm --restart=Never busybox --image=busybox:1.28 -- nslookup kubernetes.default`

`kubectl get events --field-selector involvedObject.kind=Pod`