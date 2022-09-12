# AZURE-MARKETPLACE-AGREEMENT

This repository consists of Terraform templates to run F5XC site status check.

## Usage

- Clone this repo with: `git clone --recurse-submodules https://github.com/cklewar/f5-xc-site-status-check
- Enter repository directory with: `cd f5-xc-site-status-check`
- Obtain F5XC API certificate file from Console and save it to `cert` directory
- Pick and choose from below examples and add mandatory input data and copy data into file `main.tf.example`.
- Rename file __main.tf.example__ to __main.tf__ with: `rename main.tf.example main.tf`
- Initialize with: `terraform init`
- Apply with: `terraform apply -auto-approve` or destroy with: `terraform destroy -auto-approve`

### Example Output

```bash

```

## F5XC site status check usage example



```hcl
variable "f5xc_api_url" {
  type = string
}

variable "f5xc_api_token" {
  type = string
}

variable "f5xc_tenant" {
  type = string
}

variable "f5xc_namespace" {
  type = string
}

variable "f5xc_site_name" {
  type = string
}

module "site_status_check" {
  source         = "./modules/f5xc/status/site"
  f5xc_api_url   = var.f5xc_api_url
  f5xc_api_token = var.f5xc_api_token
  f5xc_namespace = var.f5xc_namespace
  f5xc_site_name = var.f5xc_site_name
  f5xc_tenant    = var.f5xc_tenant
}
```