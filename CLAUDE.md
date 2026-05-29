# CLAUDE.md — kfp-endpoints-test

Endpoint test notebook for Kubeflow Pipelines running on DGX Spark minikube.

- API base: `http://localhost:8890/apis/v2beta1/` (forwarded by `kfp-api-portfwd.service`)
- UI: `http://localhost:8080` (forwarded by `kubeflow-portfwd.service`)

Open `notebook.ipynb` in JupyterLab and run all cells. All tests use `requests` only.

SSH tunnel: `ssh -L 8080:localhost:8080 -L 8890:localhost:8890 -L 8888:localhost:8888 <user>@spark-79b7.local`
