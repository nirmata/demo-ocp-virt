# VM Policy Validation Workflows

This directory contains GitHub Actions workflows for validating VM policies using Kyverno and NCTL.

## Workflows

### 1. vm-policy-validation.yaml
**Triggers**: Pull requests and pushes to main branch (when policies or VMs change)
**Purpose**: Validates Kyverno policy syntax and tests VMs against policies

**Features**:
- Installs Kyverno CLI
- Validates all policy syntax
- Tests positive VM (vm-good.yaml)
- Tests negative VMs (vm.yaml, vm-bad-image.yaml)
- Generates policy coverage report

### 2. nctl-scan-vm-policies.yaml
**Triggers**: Pull requests and pushes to main branch
**Purpose**: Runs NCTL scans on VM policies

**Features**:
- Installs NCTL CLI
- Scans VM policies against different test VMs
- Publishes scan results
- Validates policy structure

## Required Secrets

Add these secrets to your GitHub repository:

### For NCTL Scans
- `NIRMATA_TOKEN`: Your Nirmata API token
- `NIRMATA_URL`: Nirmata platform URL (e.g., https://nirmata.io)
- `NIRMATA_USER`: Your Nirmata username/email

### Setting up Secrets
1. Go to your repository on GitHub
2. Click on "Settings" tab
3. Click on "Secrets and variables" → "Actions"
4. Click "New repository secret"
5. Add each secret with the appropriate value

## Policy Status

| Policy | Status | Description |
|--------|--------|-------------|
| verify-annotation-enforcement | ✅ Working | Enforces required VM annotations |
| verify-image-registry | ✅ Working | Validates trusted image registries |
| verify-labeling-enforcement | ✅ Working | Enforces domain labels |
| verify-naming-convention | ✅ Working | Enforces VM naming conventions |
| verify-network-configuration-policy | ✅ Working | Validates network configuration |
| verify-resource-limits | ✅ Working | Enforces CPU/memory limits |
| verify-security-configuration | ⚠️ Audit Mode | Security context validation |
| verify-storage-control | ✅ Working | Controls VM storage allocation |

## Test VMs

- **vm-good.yaml**: Policy-compliant VM (passes 14/17 policies)
- **vm.yaml**: Original VM with policy violations (negative test)
- **vm-bad-image.yaml**: VM with invalid image registry (negative test)
- **vm-positive-test.yaml**: Alternative positive test VM

## Usage

The workflows will automatically run when:
- You push changes to the main branch
- You create a pull request to the main branch
- You modify files in the `policies/` or `vm/` directories

You can also manually trigger the workflows from the "Actions" tab in your GitHub repository.
