# yandex-ddns
A quick and basic Yandex DDNS updater written in Ruby.

## Prerequisites
- Your domain needs to be delegated to Yandex DNS and its ownership verified

- The script assumes that you have a single **A** type record pointing to **@** (root domain) in the Yandex DNS editor for your domain. The script does not currently handle multiple **A** records (if multiple records exist, the first randomly encountered one would be updated)

- Since DDNS is likely to accompany often changing public IP addresses, the default SOA record values set by Yandex are too high for fast DNS propagation. I recommend lowering **REFRESH**, **RETRY**, **MINIMUM** and **TTL** to `300` in the DNS editor

## Usage
```sh
# Install bundler
gem install bundler

# Install dependencies
bundle install

# Run the script
ruby yandex-ddns
# OR
chmod +x yandex-ddns && yandex-ddns
```

## Useful reads
- [Yandex DNS hosting](https://yandex.com/support/domain/domain/dns.html)
- [Yandex.Mail for Domain API / Documentation / Managing DNS](https://tech.yandex.com/domain/doc/concepts/api-dns-docpage/)

## Alternatives
- [populov/yandex-ddns-sh](https://github.com/populov/yandex-ddns-sh) **(Shell)**
- [thekvs/yandex-ddns](https://github.com/thekvs/yandex-ddns) **(Go)**