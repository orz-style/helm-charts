# orz-style Helm charts Repository

## Description

This site is orz-style Helm Repository.

## Usage
### Add this repository to your Helm client

```
helm repo add orz-style https://orz-style.github.io/helm-charts
```

### Get the values for configuring the chart

```
helm show values orz-style/ChartName > values.yaml
```

### Install the chart

```
helm install releaseName orz-style/ChartName --values values.yaml
```

### Uninstall the chart

```
helm uninstall releaseName
```

## Source

- [orz-style:helm-charts](https://github.com/orz-style/helm-charts)
