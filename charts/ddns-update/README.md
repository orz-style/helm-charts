# DynamicDNSUpdate

## Description

DynamicDNSUpdate script checks the current public IP and updates AWS Route53 record if IP address
change detected. This helm app runs DynamicDNSUpdate periodically.

## Installation
### Add helm repository to your Helm client

```
$ helm repo add orz-style https://orz-style.github.io/helm-charts
```

### Get the values for configuring a chart and modify it

```
$ helm show values orz-style/ddns-update > values.yaml
```

### Install the chart

```
$ helm install releaseName orz-style/ddns-update --values values.yaml
```

### Uninstall the chart

```
$ helm uninstall releaseName
```

## Parameters
### For DynamicDNSUpdate scrypt (Mandatory)

- Unless specified, DynamicDNSUpdate scrypt doesn't work

| Name | Description | Default Value |
| --- | --- | --- |
| config.dns_zone | DNS Zone info to update | "" |
| config.timezone | Timezone info | UTC-9 |
| secret.existingSecret | Existing secret name for Route53 credentials | "" |
| secret.aws_access_key_id.value | Access key id for Route53 user | "" |
| secret.aws_access_key_id.secretKey | Secret key for Access key id for Route53 in existing secret | "" |
| secret.aws_secret_access_key.value | Secret access key for Route53 user | "" |
| secret.aws_secret_access_key.secretKey | Secret key for Route53 user in existing secret | "" |

### For Kubernetes

- Optional parameters

| Name | Description | Default Value |
| --- | --- | --- |
| nameOverride | Resource name | "" |
| fullnameOverride | Resource fullname | "" |
| image.repository | Image repository | ghcr.io/orz-style/ddns-update |
| image.tag | Image tag  | "2.2.0" |
| imagePullSecrets | Pullsecret for docker registry  | [] |
| cronjob.schedule | Cron expression |  "@hourly" |
| cronjob.successfulJobsHistoryLimit | Limit of successful jobs history| 6 |
| cronjob.failedJobsHistoryLimit | Limit of failed jobs history | 10 |
| job.completions | Job completion | 1 |
| job.backoffLimit | Job backoff limit | 3 |
| persistence.accessModes | Access mode of persistent volume | ReadWriteOnce |
| persistence.anotations | Annotations of persistent volume claim | {} |
| persistence.storageClass | Storage class name | "" |
| persistence.size| Size of persistent volume | 100M |
| persistence.volumeMode| Volume mode of persistent volume | Filesystem |
| nodeSelector | Node selector | {} |
| tolerations | Tolerations | [] |
| affinity | Affinity | {} |


