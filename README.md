# Ansible Role: OpenSSL

[![Build Status](https://travis-ci.org/novuso/ansible-role-openssl.svg)](https://travis-ci.org/novuso/ansible-role-openssl)

An Ansible Role that manages SSL certificates on RedHat/CentOS/Debian/Ubuntu.

## Requirements

None.

## Installation

Using [Ansible Galaxy](https://galaxy.ansible.com/):

    ansible-galaxy install novuso.openssl

## Role Variables

Ansible variables are listed here along with their default values:

    openssl_self_signed: []

A list of self-signed certificates to generate.

    # example certificate
    openssl_self_signed:
    - name: site
      domains: ["site.com"]
      days: 365
      bits: 2048
      country: US
      state: Texas
      city: San Antonio
      organization: Acme
      unit: Web
      email: admin@site.com

The `name` field is required, and controls the name of the crt and key files.

    openssl_import_keys: []

A list of existing keys to import.

    # example import key
    openssl_import_keys:
    - name: site
      content: "-----BEGIN PRIVATE KEY-----\n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\nFQk+Jac6AkoJKaDx9ObcFDuz7SJsuMM=\n-----END PRIVATE KEY-----\n"

The `name` field controls the name of the key file. The `content` field contains the file contents.

    openssl_import_certs: []

A list of existing certificates to import.

    # example import certificate
    openssl_import_certs:
    - name: site
      content: "-----BEGIN CERTIFICATE-----\nMIIGOzCCBCOgAwIBAgIJAJsU1M0jsGAsMA0GCSqGSIb3DQEBCwUAMIGzMQswCQYD\nVQQGEwJVUzEOMAwGA1UECAwFVGV4YXMxFDASBgNVBAcMC1NhbiBBbnRvbmlvMQ8w\nDQYDVQQKDAZOb3Z1c28xETAPBgNVBAsMCFNlcnZpY2VzMRgwFgYDVQQDDA9hcHBs\naWNhdGlvbi5jb20xGjAYBgNVBAMMESouYXBwbGljYXRpb24uY29tMSQwIgYJKoZI\nhvcNAQkBFhVlbWFpbEBhcHBsaWNhdGlvbi5jb20wHhcNMTQxMTA0MDc0MTI1WhcN\nMTkxMTAzMDc0MTI1WjCBszELMAkGA1UEBhMCVVMxDjAMBgNVBAgMBVRleGFzMRQw\nEgYDVQQHDAtTYW4gQW50b25pbzEPMA0GA1UECgwGTm92dXNvMREwDwYDVQQLDAhT\nZXJ2aWNlczEYMBYGA1UEAwwPYXBwbGljYXRpb24uY29tMRowGAYDVQQDDBEqLmFw\ncGxpY2F0aW9uLmNvbTEkMCIGCSqGSIb3DQEJARYVZW1haWxAYXBwbGljYXRpb24u\nY29tMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEA2MSeMhKTO7j71wkK\nHluX2Q7IoeBBrF5MovBC51Ga9miNuRpIbVd6MaamgjrPZkUM9507w/vhKiL9v03I\nbLOh6J2EpzJE56JSXLTWzlHRKMQD67WYRDrotRPeTb6qGtYG1tFortNrX/87sXE0\n/RnWmH/F2r94QaubaTD/+boxaygE7wdUOr/jmM2WHjxbjA0Ff/B48Ksgz6c1Ohpw\nTW6tNSLVqkmFWs0QnlWEL+VBumf7OrnacZQzTZNqdK0lpiQyT24oEWq5Edx5IcWq\nnOCOfzdyISgjLWdzRm06QQIgWkcrY/pRCxmuPBtAHcw8Ex+QN8k3TfGacRkYJ0Nx\njr/GztmQ8EwQ1tyaMRAP43oHoLwtaSNknfL0k19cuYSXrR8xYSmYCfURaF99CM7P\nIsyPf7XOZhYUmHhN4gRzfIVxanx8fHpT7bOTnQ0YBubMTAOAbbj3wNKQUqrDTQbC\nBMy2vyJAdydgBQfuNR4r1Q9t4QiAfU/N960lahcWwphTFDuPsiDNt1mvUDQIejnf\ncwkxirEsq9p0rQZVc65BpBXzEDLN575BfQBuudjY5j6bPy6yRs33sPDlDK7VS/4x\nKYqpvSRdlkahwKeJRyLrUY1ZieqgcCydztK7EktuN9R37GsjRKi269cXZIe3RYnr\nEfGNVyd1vtLcZFkaiyhhco7Vyd0CAwEAAaNQME4wHQYDVR0OBBYEFDlzCe5cLLU+\nrtaYEFyT4u6ADfl8MB8GA1UdIwQYMBaAFDlzCe5cLLU+rtaYEFyT4u6ADfl8MAwG\nA1UdEwQFMAMBAf8wDQYJKoZIhvcNAQELBQADggIBAFt6TNgphCZXlh3+J2XEFDAa\nd2xmEWLKziP1IOAkBg7+RD+OIFULbuXAoH0/f8PSaGRRGm6QPHjsI67l25240M2B\nqhzpfsucQ1bohxPQiGorAVWohRmI2BFc0vSgeimCKQvcQc8LXqoqtuxiM9wGLMDc\nnWQGiRn/JATF/jc5WXqf1VPsFND9LmzxiFph7w1B6nol3DPMvc3U9YpF5iCSBwOS\n8wN0dAyxwROo6hFOWsgoZxSRCPnqPpUhkBgMrrJZYzWiW/Brt9ZIVQ/dD2K11JWe\nLCBxIaRriIzn06a6QJd1whYpgyUEvNRNWf4FoZqexny/zwPkhBibhqn9W7X4yuzt\nXtQmHGOT3B+MwYyCIrPrv63t4xoTwvH1KePPfibt5tccnrRxS4uBYK817wzUp0o9\nl4j2cfn+OM8eI9UC2KKv6giBCxzRjJC613wStNh7vKLUf5NVu6w4rJEZmKc2u9AZ\nMyPuLjrpRS+A8hcRhz4tkxZhUx7EUvN6rnfQLXIhqWaLUcb+KBL7NDOBH6/o4BY3\nGmq6QH/Saq6WucRyq2PMJWn7TOeHs3oqS6ahuBINv5OOBTUMugq9ZOgUm1Ybb12p\nKnw5VzNIFaBdUOjIb5urX2XOsJnUp8QWk5BDMktjw6mdrqeIFQlN5faG2KptGJeC\nROIGiYgif1Mf5JQNkTff\n-----END CERTIFICATE-----\n"

The `name` field controls the name of the crt file. The `content` field contains the file contents.

## Dependencies

None.

## Example Playbook

Generate a self-signed certificate.

    ---
    - hosts: app-servers
      vars:
      - openssl_self_signed:
        - name: "site"
          country: "US"
          state: "Texas"
          city: "San Antonio"
          organization: "Acme"
          unit: "Services"
          domains: ["site.com"]
          email: "email@site.com"
      roles:
      - novuso.openssl

Be sure to use [Ansible Vault](http://docs.ansible.com/playbooks_vault.html) to
encrypt variable files with sensitive information.

## License

MIT

## Author Information

John Nickell: [Novuso](http://novuso.com)
