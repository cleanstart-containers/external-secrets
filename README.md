# 🔐 CleanStart External Secrets Operator

**External Secrets Operator** is a Kubernetes operator that integrates external secret management systems (like AWS Secrets Manager, HashiCorp Vault, Google Secrets Manager, Azure Key Vault) and automatically synchronizes them as Kubernetes Secrets. This CleanStart container provides the External Secrets Operator binary for managing secrets in Kubernetes. The CleanStart External-Secrets image provides a production-ready, security-hardened container optimized for enterprise environments. Built on a minimal base OS with comprehensive security hardening, this image delivers reliable application execution with advanced security features.

**📌 CleanStart Foundation:** Security-hardened, minimal base OS designed for enterprise containerized environments.

**Image Path:** `ghcr.io/cleanstart-containers/external-secrets`

**Registry:** CleanStart Registry

---

## Overview

External Secrets Operator is a Kubernetes operator that integrates external secret management systems and automatically synchronizes them as Kubernetes Secrets. It provides a seamless way to manage secrets from various providers in a Kubernetes-native manner. This CleanStart External-Secrets container is part of the CleanStart application suite, featuring enterprise-grade security hardening, automated vulnerability management, and compliance with industry standards.

---

## About CleanStart

CleanStart is a comprehensive container registry providing security-hardened, enterprise-ready container images. Our images are designed with security-first principles, featuring minimal attack surfaces, regular security updates, and compliance with industry standards.

### About CleanStart Images

CleanStart images are built on secure, minimal base operating systems and optimized for production environments. Each image undergoes rigorous security testing, vulnerability scanning, and compliance validation to ensure enterprise-grade security and reliability.

---

## 📦 What's Included

This CleanStart container provides the External Secrets Operator binary for managing secrets in Kubernetes.

---

## 🖼️ Image Details

**Image:** `ghcr.io/cleanstart-containers/external-secrets:latest-dev`

**Key Features:**
- **User:** `clnstrt` (non-root)
- **Entrypoint:** `/usr/bin/external-secrets`
- **Default Command:** `--help`
- **Base:** CleanStart minimal container
- **SSL Certificates:** Pre-configured at `/etc/ssl/certs/ca-certificates.crt`

---

## Key Features

- **Security-First Design**: Built with minimal attack surfaces and security hardening
- **Enterprise Compliance**: Meets industry standards including FIPS, STIG, and CIS benchmarks
- **Regular Updates**: Automated security patches and vulnerability management
- **Multi-Architecture Support**: Available for AMD64 and ARM64 architectures
- **Production Ready**: Optimized for enterprise deployment and scaling
- **Comprehensive Documentation**: Detailed guides and best practices for each image
- Runs as non-root user (`clnstrt`)
- Minimal attack surface
- SSL certificates pre-configured
- No unnecessary tools or packages

---

## 🔐 Supported Providers

The External Secrets Operator supports many secret backends:

- AWS Secrets Manager
- AWS Systems Manager Parameter Store
- HashiCorp Vault
- Google Cloud Secrets Manager
- Azure Key Vault
- IBM Cloud Secrets Manager
- And many more!

---

## 🔧 Available Commands

- **Default (no command)** - Main controller mode that syncs External Secrets
- **`certcontroller`** - Manage certificates for external secrets CRDs
- **`webhook`** - Webhook server for validation
- **`completion`** - Generate shell autocompletion
- **`help`** - Help about any command

---

## 🚀 Quick Start

### Pull Commands
```bash
docker pull ghcr.io/cleanstart-containers/external-secrets:latest
docker pull ghcr.io/cleanstart-containers/external-secrets:latest-dev
```

### Test the Image
```bash
# Show help
docker run --rm ghcr.io/cleanstart-containers/external-secrets:latest-dev --help

# Certificate controller help
docker run --rm ghcr.io/cleanstart-containers/external-secrets:latest-dev certcontroller --help

# Webhook help
docker run --rm ghcr.io/cleanstart-containers/external-secrets:latest-dev webhook --help
```

### Run Commands

Basic test:
```bash
docker run -it --name external-secrets-test ghcr.io/cleanstart-containers/external-secrets:latest-dev
```

Production deployment:
```bash
docker run -d --name external-secrets-prod \
  --read-only \
  --security-opt=no-new-privileges \
  --user 1000:1000 \
  ghcr.io/cleanstart-containers/external-secrets:latest
```

---

## 📁 Directory Structure
```
external-secrets/
├── README.md                    # This file
├── kubernetes - AWS/            # Kubernetes manifests for AWS deployment
└── sample-project/              # Simple test project
    ├── README.md               # Manual testing steps
    └── Dockerfile              # Sample Dockerfile
```

---

## Architecture Support

CleanStart images support multiple architectures to ensure compatibility across different deployment environments:

- **AMD64**: Intel and AMD x86-64 processors
- **ARM64**: ARM-based processors including Apple Silicon and ARM servers

### Architecture-based Pull Commands
```bash
docker pull --platform linux/amd64 ghcr.io/cleanstart-containers/external-secrets:latest
docker pull --platform linux/arm64 ghcr.io/cleanstart-containers/external-secrets:latest
```

---

## 📚 Resources

- **[Official Documentation](https://external-secrets.io/)** - External Secrets Operator docs
- **[GitHub Repository](https://github.com/external-secrets/external-secrets)** - Source code
- **[CleanStart Images](https://cleanstart.com/)** - Official CleanStart registry
- **Provenance / SBOM / Signature:** https://images.cleanstart.com/images/external-secrets
- **Docker Hub:** https://hub.docker.com/r/cleanstart/external-secrets
- **CleanStart All Images:** https://images.cleanstart.com/images/external-secrets/details
- **CleanStart Community Images:** https://hub.docker.com/u/cleanstart

---

## Vulnerability Disclaimer

CleanStart offers Docker images that include third-party open-source libraries and packages maintained by independent contributors. While CleanStart maintains these images and applies industry-standard security practices, it cannot guarantee the security or integrity of upstream components beyond its control.

Users acknowledge and agree that open-source software may contain undiscovered vulnerabilities or introduce new risks through updates. CleanStart shall not be liable for security issues originating from third-party libraries, including but not limited to zero-day exploits, supply chain attacks, or contributor-introduced risks.

**Security remains a shared responsibility:** CleanStart provides updated images and guidance where possible, while users are responsible for evaluating deployments and implementing appropriate controls.
