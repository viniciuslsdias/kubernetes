# **Kubernetes on AWS**

## **ECR Authentication on Cluster**

```
echo "string" | base64
```

``` yaml
apiVersion: v1
kind: Secret
metadata:
  name: aws-credentials
type: Opaque
data:
  AWS_ACCESS_KEY_ID: < AWS_ACCESS_KEY_ID base64 >
  AWS_SECRET_ACCESS_KEY: < AWS_SECRET_ACCESS_KEY base64 >
  ACCOUNT_ID: < ACCOUNT_ID base64 >
  REGION: < REGION base64 >
```

```
kubectl create job --from=cronjob/ecr-update-token ecr-update-token 
```

