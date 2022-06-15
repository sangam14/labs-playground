refrences 

- [](https://kubernetes.io/docs/tutorials/security-context/pod-security-context/)
- [](https://kubernetes.io/docs/tutorials/security-context/container-security-context/)

# clone bad pod repo 
```
git clone http://github.com/sangam14/badpod.git
cd badpod/baseline 
cd disallow-capabilities
```

```
kubectl apply https://github.com/sangam14/badpod/blob/main/baseline/disallow-capabilities/resource.yaml --namespace=my-baseline-namespace

```
scan with terrascan 

```

terrascan scan -t k8s 
``


