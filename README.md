## 🎯 Overview

This repository contains a set of Kubernetes policy definitions using Kyverno to ensure that Virtual Machines deployed in OpenShift Virtualization clusters adhere to organizational standards for security, resource management, and operational excellence.

## 📋 Policy Catalog

| Policy | Category | Severity | Description |
|--------|----------|----------|-------------|
| **vm-annotation-enforcement** | 🏷️ Governance | Low | Ensure VMs have required annotations for better management and tracking |
| **verify-image-registry** | 🔒 Security | High | Ensure VM images are from trusted sources and approved registries |
| **vm-labeling-enforcement** | 🏷️ Governance | Low | Ensure VMs have required labels for proper organization and selection |
| **vm-naming-convention** | 🏷️ Governance | Medium | Ensure VMs follow consistent naming conventions |
| **vm-network-policy** | 🔒 Security | Medium | Ensure VMs have proper network configuration and policies |
| **vm-resource-limits** | 💾  Resource Management | Medium | Ensure VMs have proper CPU and memory limits defined |
| **vm-security-configuration** | 🔒 Security | High | Ensure VMs have proper security configurations and hardening |
| **vm-storage-control** | 💾 Resource Management | Medium | Restrict the size and type of storage for VM disks |
