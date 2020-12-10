# kubevious

How to delete only unmounted PVCs and PVs?
Not very elegant but bash way to delete Released PV's

```
kubectl get pv | grep Released | awk '$1 {print$1}' | while read vol; do kubectl delete pv/${vol}; done
```
