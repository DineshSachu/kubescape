# Kubescape Security Scan





## 🚀 Overview

Kubescape is a Kubernetes security scanner that checks clusters for misconfigurations and compliance issues.

## 📌 Prerequisites

- [Minikube](https://minikube.sigs.k8s.io/docs/start/) installed
- [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) installed
- [Kubescape](https://kubescape.io/docs/install/) installed

## 🔧 Getting Started

### 📂 Navigate to the Kubescape Directory

Before running the scan, navigate to your project directory:  

``` cd ~/kubescape ```

### 1️⃣ Start Minikube

Run the following command to start Minikube:

```sh
minikube start
```

Example output:

```
😄  minikube v1.34.0 on Ubuntu 24.04
✨  Using the docker driver based on existing profile
🏄  Done! kubectl is now configured to use "minikube" cluster.
```

### 2️⃣ Run Kubescape Scan

Run a security scan using the NSA framework:

```sh
kubescape scan framework nsa --format json --output ./security_findings.json
```

Example output:

```
✅  Done scanning. Cluster: minikube
✅  Scan results saved. filename: ./security_findings.json
```

### 3️⃣ Review Scan Results

The scan results will be stored in `security_findings.json`. To review the results:

```sh
cat security_findings.json | jq '.'
```

### 📊 Key Findings

| Severity | Control Name                 | Failed Resources | Compliance Score |
| -------- | ---------------------------- | ---------------- | ---------------- |
| High     | Ensure CPU limits are set    | 3                | 70%              |
| High     | Ensure memory limits are set | 3                | 70%              |
| Medium   | Prevent command execution    | 2                | 97%              |
| Medium   | Non-root containers          | 1                | 90%              |
| Medium   | Audit logs enabled           | 1                | 0%               |

To see more details, run:

```sh
kubescape scan framework nsa --verbose
```

### 📌 Next Steps

✅ Review and fix security misconfigurations in your Kubernetes cluster.
✅ Use the [Kubescape operator](https://kubescape.io/docs/install-operator/) for continuous scanning.
✅ Enable additional security features such as audit logs and etcd encryption.

## 📚 References

- [Kubescape Documentation](https://kubescape.io/docs/)
- [NSA Kubernetes Hardening Guide](https://www.nsa.gov/Press-Room/News-Highlights/Article/Article/2716980/nsa-releases-guidance-on-securing-kubernetes/)

🔒 **Secure your Kubernetes cluster today!** 🚀

