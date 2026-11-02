name: Koi

on:
  schedule:
    # Just after midnight UTC, so the koi shows the day that just ended.
    - cron: "20 0 * * *"
  workflow_dispatch:
  push:
    paths: [.github/workflows/koi.yml]

permissions:
  contents: write

concurrency: koi

jobs:
  koi:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v7
      - uses: yalongwastaken/git-koi@v1
        with:
          body: white
          output-dir: koi
      - name: Commit the koi if it changed
        shell: bash
        run: |
          git add koi/koi.gif
          if git diff --cached --quiet; then
            echo "The koi is unchanged; nothing to commit."
            exit 0
          fi
          git config user.name "github-actions[bot]"
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git commit --quiet --message "koi: draw the day's koi"
          git push --quiet

<img src="https://komarev.com/ghpvc/?username=61ZM07H36R3ML1N&style=flat-square&color=blue" alt=""/>
---



### 👨‍💻  About Me: Hi there, Im Brian Jamiel.
I am a Full Stack Developer, I mainly Develop on the M/FERN Stack.

- 🔭 Right now im an IT Assistant for a small comapny.
- 🌱 Exploring different way to build web applications.
- ⚡ In my free time, I'm building scent-map
- 📬 How to reach me: https://www.linkedin.com/in/btjamiel

---

### 🛠️ Languages and Tools :
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original-wordmark.svg" title="React" alt="React" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/materialui/materialui-original.svg" title="Material UI" alt="Material UI" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/css3/css3-plain-wordmark.svg"  title="CSS3" alt="CSS" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" title="HTML5" alt="HTML" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="JavaScript" alt="JavaScript" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/nodejs/nodejs-original-wordmark.svg" title="NodeJS" alt="NodeJS" width="40" height="40"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/mongodb/mongodb-original.svg" title="MongoDB" alt="MongoDB" width="40" height="40"/>&nbsp;
</div>



---
