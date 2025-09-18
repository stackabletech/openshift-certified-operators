
As of today, (Sep 19), you need to install this manually after the operator is installed.

See: https://github.com/stackabletech/secret-operator/pull/634#issuecomment-3312563238

---
# Source: secret-operator/templates/secretclasses.yaml
apiVersion: secrets.stackable.tech/v1alpha1
kind: SecretClass
metadata:
  name: tls
  labels:
    app.kubernetes.io/name: secret-operator
    app.kubernetes.io/instance: secret-operator
    stackable.tech/vendor: Stackable
    app.kubernetes.io/version: "0.0.0-pr640"
spec:
  backend:
    autoTls:
      ca:
        secret:
          name: secret-provisioner-tls-ca
          namespace: default
        autoGenerate: true
