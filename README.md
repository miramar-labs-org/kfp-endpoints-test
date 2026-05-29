# kfp-endpoints-test

JupyterLab notebook tests for all **Kubeflow Pipelines** REST API endpoints on the DGX Spark cluster.

## Prerequisites

- KFP deployed (`Actions → Kubeflow Deploy` in miramar-platform-gcp)
- SSH tunnel open:
  ```sh
  ssh -L 8080:localhost:8080 -L 8890:localhost:8890 -L 8888:localhost:8888 <user>@spark-79b7.local
  ```

## Endpoints tested

| Endpoint | Description |
|---|---|
| `GET /apis/v2beta1/healthz` | API server health |
| `GET /` (port 8080) | UI serving check |
| `GET /apis/v2beta1/pipelines` | List registered pipelines |
| `GET /apis/v2beta1/experiments` | List experiments |
| `GET /apis/v2beta1/runs` | List pipeline runs |

API base: `http://localhost:8890` (via `kfp-api-portfwd.service`)
UI: `http://localhost:8080` (via `kubeflow-portfwd.service`)

## Reference

- [KFP REST API v2beta1](https://www.kubeflow.org/docs/components/pipelines/reference/api/kubeflow-pipeline-api-spec/)
- [miramar-platform-gcp ENDPOINTS.md](https://github.com/miramar-labs-org/miramar-platform-gcp/blob/main/dgx/minikube/nemo/ENDPOINTS.md)
