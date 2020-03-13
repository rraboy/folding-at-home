Docker container for running [Folding@Home](http://folding.stanford.edu/)

### Usage
```bash
docker run --rm -it -p7396:7396 johnktims/folding-at-home:latest \
    --user=John_Tims --team=11675 --gpu=false --smp=true
```

The web console is available on port `7396`.

### Kube
```bash
kubectl apply -f kube.yml
xdg-open "http://$(kubectl get svc folding-at-home -o json | jq -r '.status.loadBalancer.ingress[0].ip')/"
```
