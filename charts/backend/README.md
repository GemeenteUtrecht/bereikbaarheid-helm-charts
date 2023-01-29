# Bereikbaarheid backend Helm chart

This Helm chart contains the Bereikbaarheid backend.

## Configuration

| Parameter             | Description                                                                                                                          | Default                  |
|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------|--------------------------|
| `replicaCount`        | The number of backend replicas                                                                                                       | `1`                      |
| `image.repository`    | The repository of the Docker image                                                                                                   | `bereikbaarheid-backend` |
| `image.pullPolicy`    | The Kubernetes [imagePullPolicy][] value                                                                                             | `IfNotPresent`           |
| `image.tag`           | The tag of the Docker image. If not set the tag will default to `.Chart.AppVersion`                                                  | `""`                     |
| `imagePullSecrets`    | Configuration for [imagePullSecrets][] so that you can use a private registry for your image                                         | `[]`                     |
| `nameOverride`        | Overrides the chart name for resources. If not set the name will default to `.Chart.Name`                                            | `""`                     |
| `fullnameOverride`    | Overrides the full name of the resources. If not set the name will default to `.Release.Name` - `.Values.nameOverride or Chart.Name` | `""`                     |
| `serviceAccount`      | Allows you to overwrite the "default" [serviceAccount][] for the pod                                                                 | see [values.yaml][]      |
| `podAnnotations`      | Configurable [annotations][] applied to pods                                                                                         | `{}`                     |
| `podSecurityContext`  | Allows you to set the [securityContext][] for the pod                                                                                | see [values.yaml][]      |
| `securityContext`     | Allows you to set the [securityContext][] for the container                                                                          | see [values.yaml][]      |
| `service`             | Configurable [service][] to expose the backend service.                                                                              | see [values.yaml][]      |
| `ingress.enabled`     | Expose the backend through an [ingress][]                                                                                            | `true`                   |
| `ingress.annotations` | Additional annotations on the backend ingress                                                                                        | `{}`                     |
| `ingress.hosts`       | The hosts of the ingress                                                                                                             | see [values.yaml][]      |
| `ingress.tls`         | The TLS settings of the ingress                                                                                                      | `[]`                     |
| `resources`           | Allows you to set the [resources][] for the Deployment                                                                               | `{}`                     |
| `nodeSelector`        | Configurable [nodeSelector][] so that you can target specific nodes for your backend instances                                       | `{}`                     |
| `tolerations`         | Configurable [tolerations][]                                                                                                         | `[]`                     |
| `affinity`            | Configurable [affinity][]                                                                                                            | `{}`                     |

[affinity]: https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity
[annotations]: https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/
[affinity]: https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#affinity-and-anti-affinity
[annotations]: https://kubernetes.io/docs/concepts/overview/working-with-objects/annotations/
[imagePullPolicy]: https://kubernetes.io/docs/concepts/containers/images/#updating-images
[imagePullSecrets]: https://kubernetes.io/docs/tasks/configure-pod-container/pull-image-private-registry/#create-a-pod-that-uses-your-secret
[ingress]: https://kubernetes.io/docs/concepts/services-networking/ingress/
[nodeSelector]: https://kubernetes.io/docs/concepts/configuration/assign-pod-node/#nodeselector
[resources]: https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/
[securityContext]: https://kubernetes.io/docs/tasks/configure-pod-container/security-context/#set-the-security-context-for-a-pod
[service]: https://kubernetes.io/docs/concepts/services-networking/service/
[serviceAccount]: https://kubernetes.io/docs/tasks/configure-pod-container/configure-service-account/
[tolerations]: https://kubernetes.io/docs/concepts/configuration/taint-and-toleration/
[values.yaml]: ./values.yaml
