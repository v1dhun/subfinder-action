
[Subfinder](https://github.com/projectdiscovery/subfinder) is a subdomain discovery tool developed by [ProjectDiscovery.io](https://twitter.com/pdiscoveryio). Its discovers valid subdomains for websites.

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
          telegram-chat-id: ${{ secrets.TELEGRAM_CHAT_ID }}
          telegram-token: ${{ secrets.TELEGRAM_TOKEN }}
```

## Arguments

| Input  | Description | Usage |
| :---:     |     :---:   |    :---:   |
| domains-list  | List of domains to run subfinder  | Required
| telegram-chat-id  | Telegram chat id to send notifications  | Optional
| telegram-token  | Telegram bot token to send notifications | Optional

## Contributing

Contributions are welcome!

## License

The code in this project is released under the [MIT License](LICENSE).