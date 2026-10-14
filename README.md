# Save this file in your Rahul2-5/Rahul2-5 repo at: .github/workflows/snake.yml
# It draws YOUR contribution graph as a snake and publishes it to the "output" branch,
# which the README reads from.

name: generate snake

on:
  schedule:
    - cron: "0 */24 * * *"   # once a day
  workflow_dispatch:          # lets you run it manually from the Actions tab
  push:
    branches:
      - main
      - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    steps:
      - name: generate snake svgs
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark&color_snake=#39FF14

      - name: push svgs to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
