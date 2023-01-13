# charts-demo

## install vector
helm dependency update charts/vector
helm upgrade vector charts/vector --install -f charts/vector/values.yaml --namespace monitoring
helm uninstall vector -n monitoring

## install wavefront-collector
helm dependency update charts/wavefront-collector
helm upgrade wavefront-collector charts/wavefront-collector --install -f charts/vector/values.yaml --namespace monitoring
helm uninstall wavefront-collector -n monitoring