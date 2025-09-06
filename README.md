
---

## ⚡ CI/CD Pipeline Flow
1. Developer pushes code to GitHub.
2. GitHub Actions pipeline triggers:
   - Runs tests (if any).
   - Builds Docker image.
   - Pushes image to DockerHub.
   - Deploys to **EKS cluster** using Helm.
3. App runs in Kubernetes (`dev` or `prod` namespace).

---

## 🌐 Deployment URLs
- **Dev Environment:** Deploys on branch `dev`
- **Prod Environment:** Deploys on branch `main`

Get the NodePort service:
```bash
kubectl get svc -n dev
kubectl get svc -n prod
