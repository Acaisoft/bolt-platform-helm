# Bolt Platform Umbrella Chart
Chart that holds all required components to deploy testing platform.

### Installation guide
1. Install `cert-manager` - [installation steps](https://cert-manager.io/docs/installation/helm/#steps)
2. Apply `cluster-issuer` 
```
kubectl apply -f cluster-issuer.yaml
```
`cluster-issuer.yaml`
```
apiVersion: cert-manager.io/v1
kind: ClusterIssuer
metadata:
  name: letsencrypt-prod
spec:
  acme:
    email: PLACEHOLDER
    solvers: 
    - http01:
        ingress:
          class: nginx
    privateKeySecretRef:
      name: letsencrypt-prod
    server: https://acme-v02.api.letsencrypt.org/directory
```
3. Replace all `PLACEHOLDER` in values.yaml
4. Install Bolt Platform Umbrella Chart
5. Wait for everything to start and you should be able to access bolt platform.