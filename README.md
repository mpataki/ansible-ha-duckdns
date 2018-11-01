# ansible-ha-duckdns

[DuckDNS](https://www.duckdns.org/) is a service that grants users a subdomain of duckdns.org as well as an API that can be used to update the public IP address that the subdomain points to. This effectively allows common home dynamic IPs to be pointed to by the subdomain, even if they change.

This ansible role consumes the subdomain and auth token as variables and uses them to create a cron job which will keep the DuckDNS up to date with your pi's IP address.

This is a part of a suite of ansible roles that can help turn your Pi into a pretty capable home monitoring/automation hub.

## Requirements

Really this should work on any debian based system, but has been tested on a Raspberry Pi running Hassbian.

## Role Variables

- `duck_subdomain`: This is something like `my_house`, as in, `my_house.duckdns.org`
- `duck_token`: This is the auth token that is provided by DuckDNS.

## Dependencies

You first need to sign up for DuckDNS and obtain a token.

## Example Playbook

```yml
    - hosts: servers
      vars:
        duck_subdomain: <your-domain>
        duck_token: <your-token>
      roles:
         - role: mpataki.ha-duckdns
```

## License

MIT

