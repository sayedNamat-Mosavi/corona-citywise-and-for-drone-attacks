# corona-citywise-and-for-drone-attacks
corona citywise and for drone attacks[task -assignment 02]
name: Check Markdown links

on:
  push:
    branches:
      - master
  schedule:
    # Run everyday at 9:00 AM (See https://pubs.opengroup.org/onlinepubs/9699919799/utilities/crontab.html#tag_20_25_07)
    - cron: "0 9 * * *"

jobs:
  markdown-link-check:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - uses: gaurav-nelson/github-action-markdown-link-check@v1
      with:
        use-quiet-mode: 'no'
        use-verbose-mode: 'yes'
        config-file: '.mlc_config.json'
        file-path: './README.md'
