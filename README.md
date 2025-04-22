
---

# GenAI Full Stack Project with GitOps Deployment

This is a full-stack GenAI application with a frontend (Next.js + TailwindCSS) and backend (Python/Flask). It is deployed using GitOps with ArgoCD and CI using GitHub Actions. Kubernetes setup is done on an EC2 instance provisioned via Terraform.

## Features

- Frontend: Next.js, Tailwind CSS
- Backend: Flask with AI utilities
- CI: GitHub Actions (build, push images, update manifests)
- CD: ArgoCD (auto-sync manifests)
- Infra: Terraform for provisioning EC2 and bootstrapping k8s & ArgoCD
- Multi-env support: Kustomize for `dev` and `prod`

## Project Structure

```
backend/        # Flask app
frontend/       # Next.js app
manifest/       # K8s manifests with Kustomize (base + overlays)
```

## Deployment Flow

1. Push code to `main` branch
2. GitHub Actions builds Docker images, pushes them to Docker Hub
3. Manifests are updated with new image tags
4. ArgoCD auto-syncs and deploys the latest version

## Setup

- Use Terraform to create EC2 and install k8s + ArgoCD
- Clone this repo on EC2 and apply Kustomize overlays using ArgoCD

## Environments

- `/manifest/base` - shared config
- `/manifest/overlays/dev` - dev config
- `/manifest/overlays/prod` - prod config

---


---

## ☁️ Infra (Terraform + EC2 + ArgoCD + K8s)

- Terraform provisions EC2 instance
- A script bootstraps Kubernetes via `kind` and installs ArgoCD
- ArgoCD syncs apps from GitHub repo

---



## 👨‍💻 Author

**Sikander Kumbhar**  
GitHub: [@SIKANDERKUMBHAR](https://github.com/SIKANDERKUMBHAR)  
LinkedIn: [LinkedIn Profile](https://www.linkedin.com/in/sikander-ali-9792932a8/)

---
