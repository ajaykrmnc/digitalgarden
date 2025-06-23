---
{"dg-publish":true,"permalink":"/coding/productivity/the-economist-magazine-to-kindle/","dgPassFrontmatter":true,"created":"2025-05-28T19:25:35.338+05:30","updated":"2025-06-19T21:06:03.614+05:30"}
---

Daily Automation of TheEconomist Magazine to my Using Monkfishare the Economist github repo. Since I can't afford to pay around 10$ per magazine I find a way with the open source github repo. Thanks GPT for a being a great tool.

```zsh
#!/bin/bash

# === Configurations ===
REPO_PATH="$HOME/Desktop/KindleAutomate/economist-epub" # Local path to clone the repo
GIT_REPO_URL="https://gitlab.com/Monkfishare/2025.git"
KINDLE_EMAIL="pramodshah6797_37Oxxx@kindle.com"
SENDER_EMAIL="xxx@gmail.com" # Must be on Amazon whitelist

# === Step 1: Clone or pull latest changes ===

if [ ! -d "$REPO_PATH" ]; then
git clone "$GIT_REPO_URL" "$REPO_PATH"
else
cd "$REPO_PATH" || exit
git pull
fi
  
# === Step 2: Find the latest EPUB file ===
YYY=$(date +%Y)
  
cd "$REPO_PATH/TE/$YYY" || exit
latest_folder=$(ls -d [0-9][0-9][0-9][0-9]-[0-9][0-9]-[0-9][0-9] | sort -r | head -n 1)
cd "$latest_folder" || exit
latest_epub=$(ls -t *.epub | head -n 1)

  

if [ -z "$latest_epub" ]; then
echo "No EPUB file found."
exit 1
fi

# === Step 3: Send using Calibre ===
# Ensure calibre is installed. On macOS, you can install it via Homebrew:
# brew install --cask calibre
# calibre-smtp is included with Calibre. After installation, it should be available in your PATH.
# If calibre-smtp is not in your PATH, specify the full path below:
#

  

/Applications/calibre.app/Contents/MacOS/calibre-smtp \
--attachment "$latest_epub" \
--relay smtp.gmail.com \
--port 587 \
--username "ajaykg6917@gmail.com" \
--password "xxxx xxxx xxxx xxxx" \
"$SENDER_EMAIL" "$KINDLE_EMAIL" \
"Your Daily Economist" "Attached is the latest Economist EPUB."
```

