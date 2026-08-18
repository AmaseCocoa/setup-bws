# setup-bws
> [!WARNING]
> We are not affiliated with bitwarden inc.  this actions is unofficial. please be careful!

Unofficial Actions to setup latest or specific bitwarden secrets cli

## Arguments
- **version**: version of bws. default is `latest`
- **github-token**: github token to fetch from api. for avoid rate limit.

## Usage
```yaml
name: Fetch Secrets Example

on:
  push:
    branches: [ main ]

jobs:
  run-build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v7

      - name: Setup BWS
        uses: AmaseCocoa/setup-bws@v1

      - name: Fetch Secret from Bitwarden
        env:
          BWS_ACCESS_TOKEN: ${{ secrets.BWS_ACCESS_TOKEN }}
        run: |
          bws run - echo ${HOGEHOGE_SECRET}
```
