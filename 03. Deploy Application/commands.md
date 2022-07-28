/### Kubectl commands

##### apply manifests
    kubectl apply -f nginx-deployment.yaml
    kubectl apply -f nginx-service.yaml

##### labels
    kubectl get svc
    kubectl describe svc {svc-name}
    kubectl get ep

    kubectl get svc --show-labels
    kubectl get svc -l app=nginx 

    kubectl get pod --show-labels
    kubectl get pod -l app=nginx
    kubectl logs -l app=nginx

    kubectl get pod -n kube-system --show-labels
    kubectl logs -n kube-system -l="name=weave-net" -c weave

    kubectl get node —show-labels


##### scaling deployments
    kubectl scale --help
    kubectl scale deployment {depl-name} --replicas 4
    kubectl scale deployment {depl-name} --replicas 3

    kubectl scale deployment {depl-name} --replicas 5 --record
    kubectl rollout history deployment {depl-name}


##### create pods
    kubectl run test-nginx-service --image=busybox
    kubectl exec -it {pod-name} -- bash

#### verify service connection
    after create pods, entering pod by:
    kubectl exec -it test-nginx-svc -- bash
    then in pod:
    curl http://10.98.148.178:8080
    curl nginx-service:8080

