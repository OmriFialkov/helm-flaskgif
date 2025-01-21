---

## Helm Flask GIF Repository

Welcome to the **Helm Flask GIF Repository**! This repository hosts a Helm chart for deploying a Flask application that serves GIFs on a Kubernetes cluster. This chart simplifies deploying and managing the application with Helm.

### What is Helm?

[Helm](https://helm.sh) is a package manager for Kubernetes. It allows you to define, install, and manage Kubernetes applications as Helm charts. Helm charts are reusable application templates that encapsulate Kubernetes resources.

---

## Repository Purpose

This repository contains:
- A Helm chart (`helm-flask`) for deploying a Flask-based application.
- Instructions for adding this Helm chart repository to your Helm setup.
- Files needed to make the repository functional with `helm repo` commands.
- you can access the github page in : https://omrifialkov.github.io/helm-flaskgif/

---

## How to Use This Repository

### 1. **Prerequisites**
Before you begin, make sure you have:
- **Helm** installed on your local machine.  
  Install Helm by following the [official instructions](https://helm.sh/docs/intro/install/). For example, on Linux:
  ```bash
  curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
  ```
- **kubectl** installed and configured to connect to your Kubernetes cluster.  
  Refer to the [kubectl installation guide](https://kubernetes.io/docs/tasks/tools/) for setup instructions.

---

### 2. **Add the Repository**

To add this Helm chart repository to your local Helm setup, run:
```bash
helm repo add helmflask https://omrifialkov.github.io/helm-flaskgif
helm repo update
```

This will add the `helmflask` repository and sync its contents with your local Helm configuration.

---

### 3. **Install the Helm Chart**

To install the Helm chart in your Kubernetes cluster:
```bash
helm install helm-flask helmflask/helm-flask
```

This command:
- Installs the `helm-flask` chart from the `helmflask` repository.
- Creates the Kubernetes resources defined in the chart, like Pods, Services, etc.

---

### 4. **Verify the Deployment**

Once installed, verify the application is running by checking the Kubernetes resources created:
```bash
kubectl get all
```

To list all Helm releases installed in your cluster:
```bash
helm list
```

---

### 5. **Uninstall the Chart**

To uninstall the Helm chart and clean up the resources it created:
```bash
helm uninstall helm-flask
```

This command will remove the release named `helm-flask` and delete all associated Kubernetes resources.

---

### 6. **Basic Helm Commands**

Here are some useful Helm commands to manage your charts and releases:

- **List installed Helm releases:**
  ```bash
  helm list
  ```
- **Search for available charts in a repo:**
  ```bash
  helm search repo helmflask
  ```
- **Show chart details:**
  ```bash
  helm show chart helmflask/helm-flask
  ```
- **Upgrade an installed release:**
  ```bash
  helm upgrade helm-flask helmflask/helm-flask
  ```
- **Rollback to a previous release:**
  ```bash
  helm rollback helm-flask <revision_number>
  ```
- **Check Helm version:**
  ```bash
  helm version
  ```

---

### 7. **Chart Development**

If you're looking to modify or expand this chart, you can:
1. Clone this repository:
   ```bash
   git clone https://github.com/omrifialkov/helm-flaskgif.git
   cd helm-flaskgif
   ```
2. Edit the chart files inside the `helm-flask` directory.
3. Test the chart locally using:
   ```bash
   helm install test-release ./helm-flask --dry-run --debug
   ```

---

### 8. **About the Flask Application**

This Helm chart deploys a simple Flask application that serves GIFs. You can customize the application, configuration, or Kubernetes resources by modifying the chart's `values.yaml` file.

---

## Repository Contents

- **`index.yaml`**: The Helm repository index file, listing the available charts and versions.
- **`helm-flask-<version>.tgz`**: The packaged Helm chart for deployment.
- **`index.html`**: GitHub Pages file displaying repository usage instructions.

---

### Need Help?

For any questions or issues, feel free to open an issue in this repository or consult the [Helm documentation](https://helm.sh/docs/).

---
