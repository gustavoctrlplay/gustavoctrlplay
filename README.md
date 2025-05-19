- 👋 Olá, eu sou @gustavoctrlplay
- 👀 Eu sou interessado em animes, jogos e programação web
- 🌱 Programação web
- 📫 gustavo@gmail.com
- ⚡ Fun fact: Sou diamante no lol

name: GitHub-Profile-3D-Contrib

on:
  schedule: # Run at 03:00 JST / 18:00 UTC
    - cron: "0 18 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest
    name: generate-github-profile-3d-contrib
    steps:
      - uses: actions/checkout@v4
      - uses: yoshi389111/github-profile-3d-contrib@latest
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}
      - name: Commit & Push
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          if git commit -m "generated"; then
            git push
          fi



<!---
gustavoctrlplay/gustavoctrlplay is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
