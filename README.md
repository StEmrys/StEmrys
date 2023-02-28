<h2 align="center">Hi 👋! My name is Emre<br> and I'm a QA Automation Test Engineer, <br>from FRANCE</h2>

###

<br clear="both">

<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?hide_title=true&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=moltack&locale=en&hide_border=false&username=St" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=onedark&hide_border=false&username=St" height="150" alt="languages graph"  />
</div>

###

<br clear="both">

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="30" width="42" alt="java logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/canva/canva-original.svg" height="30" width="42" alt="canva logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="30" width="42" alt="git logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" height="30" width="42" alt="github logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/photoshop/photoshop-plain.svg" height="30" width="42" alt="photoshop logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" height="30" width="42" alt="postgresql logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/slack/slack-original.svg" height="30" width="42" alt="slack logo"  />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" height="30" width="42" alt="vscode logo"  />
</div>

###

<br clear="both">

<img align="right" height="0" src=""  />

###

<br clear="both">

<div align="center">
  <a href="2144" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=7289DA&logoColor=white&labelColor=&style=plastic" height="35" alt="discord logo"  />
  </a>
  <a href="https://www.linkedin.com/in/soydemir-emre-559641237/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=plastic" height="35" alt="linkedin logo"  />
  </a>
  <a href="eosoydemir@outlook.fr" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Outlook&logo=microsoft-outlook&label=&color=0078D4&logoColor=white&labelColor=&style=plastic" height="35" alt="microsoft-outlook logo"  />
  </a>
</div>

###
name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

###

