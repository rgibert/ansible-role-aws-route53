# AWS Route 53

Setup domain(s) using AWS's Route 53

## Requirements

- none

## Role Variables

| Variable | Default | Description |
| aws_route53_dns_ttl | 86400 | TTL for all the domain settings |
| aws_route53_dns_domain_defs | | List of domain settings to setup, see example below |
| aws_route53_access_key_id | | AWS Access Key ID |
| aws_route53_secret_access_key | | AWS Secret Access Key |

## Dependencies

- none

## Example Playbook

```
- hosts:
    - localhost
  roles:
    - role: rgibert.aws-route53,
      aws_route53_dns_domain_defs:
        - dns: "gibert.ca"
          val: "1 aspmx.l.google.com., 10 aspmx2.googlemail.com., 10 aspmx3.googlemail.com., 5 alt1.aspmx.l.google.com., 5 alt2.aspmx.l.google.com."
          type: "MX"
      aws_route53_access_key_id: "AccessKeyID",
      aws_route53_secret_access_key: "SecretAccessKey"
```

## License

GPLv3

## Author Information

Richard Gibert <richard@gibert.ca>
