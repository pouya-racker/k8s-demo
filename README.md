# k8s-demo

## Useful commands/tools

Browse an internal service

`kubectl run -it --rm --restart=Never curl --image=curlimages/curl -- curl SERVICE_NAME`

Check cluster's DNS service

`kubectl run -it --rm --restart=Never busybox --image=busybox:1.28 -- nslookup kubernetes.default`

See all the pod level cluster events

`kubectl get events --field-selector involvedObject.kind=Pod`

Check for differences in nodes

`kubectl get nodes -o custom-columns=NAME:.metadata.name,OS:.status.nodeInfo.osImage,KERNEL:.status.nodeInfo.kernelVersion,RUNTIME:.status.nodeInfo.containerRuntimeVersion,KUBELET:.status.nodeInfo.kubeletVersion,KUBEPROXY:.status.nodeInfo.kubeProxyVersion`

Show node conditions

`kubectl get nodes -o go-template='{{range .items}}{{$node := .}}{{range .status.conditions}}{{$node.metadata.name}}{{": "}}{{.type}}{{":"}}{{.status}}{{"\n"}}{{end}}{{end}}'`