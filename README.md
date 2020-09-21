
[Subfinder](https://github.com/projectdiscovery/subfinder) is a subdomain discovery tool developed by [ProjectDiscovery.io](https://twitter.com/pdiscoveryio). It helps to discover valid subdomains from targets given.

## Usage
```
name: "Subdomain finding using subfinder"

on:
  workflow_dispatch:
  schedule:
    - cron: "0 0 * * FRI"

jobs:
  worker:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: v1dhun/subfinder-action@master
        with:
          domains-list: "domains.txt"
          config-list: "config.yaml"
          check-alive: "true"
          telegram-chat-id: ${{ secrets.TELEGRAM_CHAT_ID }}
          telegram-token: ${{ secrets.TELEGRAM_TOKEN }}
```

## Arguments

| Input  | Description | Usage |
| :---:     |     :---:   |    :---:   |
| domains-list  | List of domains to run subfinder | Required
| check-alive  | To check host is alive or not using [httpx](https://github.com/projectdiscovery/httpx) | Optional
| telegram-chat-id  | Telegram chat id to send notifications  | Optional
| telegram-token  | Telegram bot token to send notifications | Optional
| config-list | Configuration file for API Keys, etc | Optional

## Contributing

Contributions are welcome!

## License

The code in this project is released under the [MIT License](LICENSE).
