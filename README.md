
## Deploy traffic-manager on GKE

intro doc: https://starquest.feishu.cn/docx/It8rdMpSSodQYrxhIWwcZYz1nse

0. first, install telepresence on Mac

```
# Intel Macs

# 1. Download the latest binary (~105 MB):
sudo curl -fL https://app.getambassador.io/download/tel2oss/releases/download/v2.18.0/telepresence-darwin-amd64 -o /usr/local/bin/telepresence

# 2. Make the binary executable:
sudo chmod a+x /usr/local/bin/telepresence

# Apple silicon Macs

# 1. Download the latest binary (~101 MB):
sudo curl -fL https://app.getambassador.io/download/tel2oss/releases/download/v2.18.0/telepresence-darwin-arm64 -o /usr/local/bin/telepresence

# 2. Make the binary executable:
sudo chmod a+x /usr/local/bin/telepresence
```

Then deploy or upgrade traffic-manager on dev GKE

1. deploy

```
telepresence helm install -f dev/values.yaml --context dreampal-dev-us-east1
telepresence helm install -f dev/values.yaml --context dreampal-dev-us-central1
```

2. upgrade

```
telepresence helm upgrade -f dev/values.yaml --context dreampal-dev-us-east1
telepresence helm upgrade -f dev/values.yaml --context dreampal-dev-us-central1
```
