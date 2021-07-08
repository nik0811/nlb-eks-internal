# Nlb-Eks-Internal
Internal NlB in Private Subnet AWS

```
apiVersion: v1
kind: Service
metadata:
name: nikhil-keycloak
annotations:
    kubernetes.io/ingress.class: nlb
    service.beta.kubernetes.io/aws-load-balancer-type: nlb
    service.beta.kubernetes.io/aws-load-balancer-backend-protocol: http
    service.beta.kubernetes.io/aws-load-balancer-internal: "true"
    service.beta.kubernetes.io/aws-load-balancer-internal: 0.0.0.0/0
spec:
   ports:
    - port: 80
      targetPort: http
      protocol: TCP
   type: LoadBalancer
   selector:
       app.kubernetes.io/component: keycloak
       app.kubernetes.io/instance: nonprod-keycloak
       app.kubernetes.io/name: keycloak 
```
