## how to manually install/uninstall the chart
```
helm dependency build /Users/steveliu/okta/docker/repositories/wavefront-collector/helm-charts/

helm upgrade --install wavefront-collector -f /Users/steveliu/okta/docker/repositories/wavefront-collector/helm-charts/spinnaker-auw2n-values.yaml /Users/steveliu/okta/docker/repositories/wavefront-collector/helm-charts/ --namespace monitoring

helm uninstall wavefront-collector -n monitoring
```


## how to push the token
```
kubectl get secret wavefront-collector -n monitoring -o jsonpath="{.data.api-token}" | base64 --decode
echo -n 'your_token' | openssl base64
kubectl edit secret wavefront-collector -n monitoring 
kubectl get secret wavefront-collector -n monitoring -o jsonpath="{.data.api-token}" | base64 --decode
```
