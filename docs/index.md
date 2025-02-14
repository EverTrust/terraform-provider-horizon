---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "horizon Provider"
subcategory: ""
description: |-
  The Horizon provider is used to interact with the Horizon API. It can manage the lifecycle of certificates and other resources.
---

# horizon Provider

The Horizon provider is used to interact with the Horizon API. It can manage the lifecycle of certificates and other resources.

## Example Usage

```terraform
terraform {
  required_providers {
    horizon = {
      source = "registry.terraform.io/evertrust/horizon"
    }
  }
}

# With creds authentication
provider "horizon" {
  alias = "with-creds"

  endpoint = "https://horizon.company.com"
  username = "username"
  password = "password"
}

# With certificate authentication
provider "horizon" {
  alias    = "with-cert"
  endpoint = "https://horizon.company.com"
  cert     = "----BEGIN CERTIFICATE-----\n...\n----END CERTIFICATE-----\n"
  key      = "----BEGIN RSA PRIVATE KEY-----\n...\n----END RSA PRIVATE KEY-----"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `endpoint` (String) Horizon URL, with protocol (https://) and without trailing slash. Required.

### Optional

- `ca_bundle_pem` (String) PEM-encoded CA bundle to use for TLS certificate verification. Optional.
- `client_cert_pem` (String) Client certificate to use for authentication. Required when client_key_pem is provided.
- `client_key_pem` (String) Private key associated with the client certificate. Required when client_cert_pem is provided.
- `password` (String) Local account password. Required when username is provided.
- `proxy` (String) HTTP proxy URL to use for requests. Optional.
- `skip_tls_verify` (Boolean) Skip TLS certificate verification. Optional, default to false. Note that this is not recommended in production.
- `username` (String) Local account identifier. Required when password is provided.
