# Zerops x Metabase


```yaml
#yamlPreprocessor=on
project:
  name: metabase
services:
  - hostname: metabase
    type: java@21
    envSecrets:
      MB_INSTANCE_ID: <@generateRandomBytes(<16>) | toHex>
    verticalAutoscaling:
      ram: 3
  - hostname: db
    type: postgresql@16
    mode: NON_HA
```
