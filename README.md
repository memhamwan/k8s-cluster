```bash
flux bootstrap github \
--owner=memhamwan \
--repository=k8s-cluster \
--path=kubernetes
```

```bash
flux create kustomization sops-secrets \
--source=flux-system \
--path=kubernetes \
--prune=true \
--interval=10m \
--decryption-provider=sops \
--decryption-secret=sops-age
```
