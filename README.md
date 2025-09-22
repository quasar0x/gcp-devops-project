# GCP DevOps Project – Flask → Docker → Cloud Build → GKE

This repo demonstrates a minimal, production‑style CI/CD pipeline on Google Cloud:

* **App**: Python/Flask (`app.py`)
* **Container**: Docker (`Dockerfile`)
* **Registry**: `gcr.io/kodekloud-gcp-training-472323/...` (GCR, Artifact Registry–backed)
* **Cluster**: Google Kubernetes Engine **Standard** cluster `gcp-devops-project` in zone `us-central1-a`
* **Envs**: two Kubernetes namespaces → `gcp-devops-dev`, `gcp-devops-prod`
* **CI/CD**: 2 Cloud Build triggers (dev/prod) running separate `cloudbuild.yaml` which build, push, and deploy via **gke-deploy**
* **Security**: dedicated Cloud Build service accounts per env; least‑privilege IAM; namespace‑scoped Kubernetes RBAC