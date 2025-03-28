datahub-frontend
================
A Helm chart for datahub-frontend

Current chart version is `0.2.0`

## Chart Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| datahub.play.mem.buffer.size | string | `"10MB"` |  |
| existingGmsSecret | object | {} | Reference to GMS secret if already exists |
| exporters.jmx.enabled | boolean | false |  |
| extraEnvs | Extra [environment variables][] which will be appended to the `env:` definition for the container | `[]` |
| extraVolumes | Templatable string of additional `volumes` to be passed to the `tpl` function | "" |
| extraVolumeMounts | Templatable string of additional `volumeMounts` to be passed to the `tpl` function | "" |
| fullnameOverride | string | `"datahub-frontend"` |  |
| global.datahub_analytics_enabled | boolean | true |  |
| global.datahub.gms.port | string | `"8080"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"linkedin/datahub-frontend-react"` |  |
| image.tag | string | `"head"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.extraLabels | object | `{}` | provides extra labels for ingress configuration |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths | list | `[]` |  |
| ingress.hosts[0].redirectPaths | list | `[]` |  |
| ingress.tls | list | `[]` |  |
| livenessProbe.initialDelaySeconds | int | `60` |  |
| livenessProbe.periodSeconds | int | `30` |  |
| livenessProbe.failureThreshold | int | `4` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| oidcAuthentication.enabled | boolean | `false` | Enable [OIDC authentication](https://datahubproject.io/docs/authentication/guides/sso/configure-oidc-react) |
| oidcAuthentication.provider | string | `""` | One of the supported OIDC providers: [google](https://datahubproject.io/docs/authentication/guides/sso/configure-oidc-react-google), [okta](https://datahubproject.io/docs/authentication/guides/sso/configure-oidc-react-okta), or [azure](https://datahubproject.io/docs/authentication/guides/sso/configure-oidc-react-azure) |
| oidcAuthentication.clientId | string | `""` | A unique identifier for your application with the identity provider |
| oidcAuthentication.clientSecret | string | `""` | A shared secret to use for exchange between you and your identity provider |
| oidcAuthentication.clientSecretRef.secretRef | string | `"nil"` | Optional, this is the reference to the shared secret to use for exchange between you and your identity provider |
| oidcAuthentication.clientSecretRef.secretKey | string | `"nil"` | Optional, this is the key of the shared secret to use for exchange between you and your identity provider |
| oidcAuthentication.oktaDomain | string | `""` | Okta domain, e.g. `dev-12345.okta.com`; needed only if `provider` is set to `okta` |
| oidcAuthentication.azureTenantId | string | `""` | Azure directory (tenant) ID; neede only if `provider` is set to `azure` |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| readinessProbe.initialDelaySeconds | int | `60` |  |
| readinessProbe.periodSeconds | int | `30` |  |
| readinessProbe.failureThreshold | int | `4` |  |
| replicaCount | int | `1` |  |
| revisionHistoryLimit | int | `10` |  |
| lifecycle | object | `{}` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `9001` |  |
| service.nodePort | int | `""` |  |
| service.type | string | `"LoadBalancer"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `nil` |  |
| serviceMonitoring.create | bool | `false` | If set true and `global.datahub.monitoring.enablePrometheus` is set `true` it will create a ServiceMonitor resource |
| tolerations | list | `[]` |  |
| global.elasticsearch.host | string | `"elasticsearch"` |  |
| global.elasticsearch.port | string | `"9200"` |  |
| global.kafka.bootstrap.server | string | `"broker:9092"` |  |
| datahub.metadata_service_authentication.enabled | bool | `false` | Whether Metadata Service Authentication is enabled. |
| global.datahub.metadata_service_authentication.systemClientId | string | `"__datahub_system"` | The internal system id that is used to communicate with DataHub GMS. Required if metadata_service_authentication is 'true'. |
| global.datahub.metadata_service_authentication.systemClientSecret.secretRef | string | `nil` | The reference to a secret containing the internal system secret that is used to communicate with DataHub GMS. Required if metadata_service_authentication is 'true'. |
| global.datahub.metadata_service_authentication.systemClientSecret.secretKey | string | `nil` | The key of a secret containing the internal system secret that is used to communicate with DataHub GMS. Required if metadata_service_authentication is 'true'. |
