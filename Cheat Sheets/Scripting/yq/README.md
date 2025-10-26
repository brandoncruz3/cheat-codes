# yq

## Cheatsheets

Render the entire yaml file:

```bash
yq -r '.'
```

Access the `microservices` key:

```bash
yq -r '.microservices'
```

Append something at the bottom of the file:

```bash
yq -i '.external_secrets = {"enabled": false}' test.yaml
```

Delete a key with its contents:

```bash
yq -i 'del(.microservice.secrets)' test.yaml
```

Inject values from another file:

```bash
yq -i ".microservice.env = load(\"staging.yaml\") | .microservice.env" test.yaml.yaml
```

Add new data:

```bash
yq -i '.microservice.aws = {"accountId": "000000000000","region": "eu-west-1","eks": {"clusterId": "xxxxxxxxxxxxxxx"}}' test.yaml
```

Sort keys under microservices

```bash
yq -i '.microservice |= (to_entries | sort_by(.key) | from_entries)' test.yaml
```
