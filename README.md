# 🚦 Dnsmasq Config Check GitHub Action

GitHub Action для проверки конфигурационных файлов `dnsmasq` через Docker.

Полезен при автоматической генерации списков доменов и конфигурации DNS-фильтрации.

---

## 📦 Использование

Пример workflow:

```yaml
name: Check Dnsmasq config

on:
  push:
    paths:
      - "*.conf"
  workflow_dispatch:

jobs:
  check-dnsmasq:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run Dnsmasq config check
        uses: mizoil/dnsmasq-action@main
        with:
          file: "dnsmasq.conf"
          version: "2.89"
