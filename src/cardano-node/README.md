# cardano node

Creates a single of producer or relay cardano node.

---

# Important Notes:
- **Note: Use this template at your own risk. It is your responsibility to secure your kubernetes cluster and deployments. This template does not offer protection for your certificates, nor does it offer any security advantages or guarentees.**

- **Note: it is recommended to only run a single producer node**

---

# Options

| name | description | default |
| ---- | ----------- | ------- |
| configsTopologyJson | topology json file contents | []() |
| metricsPort | port to use for metrics | 12798 |
| nodeCount | number of replicas to create, note that running more than one producer node is not recommended | 1 |
| nodePort | port to use for cardano node | 4444 |
| nodeVersion | the version of cardano-node to run | 1.26.2 |
| serviceName | name for the service that exposes the node(s) within the cluster | {{ .Release.Name }} |
| stateVolumeStorageClassName | the storage class to use for storing state in | default |
| stateVolumeAccessMode | the access mode for state volume | ReadWriteOnce |
| stateVolumeSize | the size for the state volume | 24Gi |
| requestsCpu | the amount of cpu requested for cardano node | 2000m |
| requestsMemory | the amount of memory requested for cardano node | 4Gi |
| limitsCpu | the max amount of cpu cardano node can consume, note that exceeding this limit will cause cardano node to be throttled by kubernetes | 2000m |
| limitsMemory | the max amount of memory each cardano node can consume, note that exceeding this amount will cause kubernetes to kill your pods | 4Gi |
| nodeType | the type of node to start, relay or producer | relay |
| producerCertificatesKesSKey | the kes signing key, required for producer nodes, you are responsible for your certificates. | none |
| producerCertificatesVrfSKey | the vrf signing key, required for producer nodes, you are responsible for your certificates. | none |
| producerCertificatesNodeCert | the node operating certificate, required for producer nodes, you are responsible for your certificates. | none |
