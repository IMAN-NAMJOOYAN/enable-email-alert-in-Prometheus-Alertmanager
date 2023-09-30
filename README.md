# enable-email-alert-in-Prometheus-Alertmanager
We have using prometheus-stack from "https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack".
Before enabling email alert you can customize helm default values.
We prepare a customize default values that enable email alert in prometheus alertmanager.
you can pass customize default values by :
```
helm install prometheus-stack kube-prometheus-stack-46.8.0.tgz --version 46.8.0 -n monitoring -f def-val.yaml --create-namespace
```
Note: After deploying prometheus-stack check alertmanager configuration.
```
kubectl get secrets -n monitoring alertmanager-prometheus-stack-kube-prom-alertmanager -o yaml|grep alertmanager.yaml|awk {'print $2'}|base64 -d -w0
```

![image](https://github.com/IMAN-NAMJOOYAN/enable-email-alert-in-Prometheus-Alertmanager/assets/16554389/f891085b-96b6-4551-9703-f01bce243fc2)
