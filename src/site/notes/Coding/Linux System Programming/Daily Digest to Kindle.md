---
{
  "dg-publish": true,
  "permalink": "/coding/linux-system-programming/daily-digest-to-kindle/",
}
---

_Hello everyone._
_I just wanted to share something beautiful thing I've realised that feels
good about learning programming stuff I feel how fulfilling it is to apply my
programming knowledge to a real problem I genuinely wanted to solve._

_The problem was really very simple: To daily send tech/finance/national news
& some article from different sites to my e-ink device Kindle in epub format
without opening my laptop or doing it manually. \[FYI] the only way to send
file to Kindle Device is via kindle email._

_But it opens a complete new whole lot of learning along the way. I am listing
all the cool stuffs learnt iteratively on this way._

\*I started with solving a very simple problem of sending this theEconomist
Magazine \[Weekly Magazine] to my kindle [[Coding/Productivity/TheEconomist
Magazine to Kindle\|TheEconomist Magazine to Kindle]]

> [!Note]
> **Calibre** - A famous ebook software management tools and its cli tools
> like ebook-convert(converting html or .md to epub) and calibre-smtp(sending
> a mail). Also I discovered Kovid Goyal brain behind Calibre.
> **SMTP server**: We can set the gmail SMTP server to send one email to
> another email by assigning a port on a sever and using our gmail app
> password.
> **Cron Job & Github Actions:** Cron Job: A .yml file for automating repeated
> job daily Great for automating cron job daily without manual job for opening
> laptop daily connecting to the internet and visiting for every site.
> **Web-srcapping**: Scrapped a whole blog website and save it to the .csv
> file all the important blog links associated to it.
> **HTML-parsing** : Learnt on the way how to parse different sites using dom
> manipulation and querying for different element for different sites
> **Tamper-monkey**: \[ A Chrome extension] Initially I thought tampermonkey
> will help in webparsing by visiting website and manipulating the dom element
> on the browser. It helps automatically when a sites loads it can remove all
> the unnecessary content on any website like ads, side menus.
> **Python Library like BeautifulSoup**: Then I learnt a better way by using
> beautifulSoup and using python library like requests
> **RSS Feeds**: Intially I throught different links can be fetched by
> web-parsing but later I realized that the recent blogs and updated content
> of the website are managed through the RSS Feeds.
> **Epub Formatting** : Yes a lot of learning also involved how epub file is
> created and how to format which suits for Kindle. Also I faced a lot of
> error E999 \[Internal Error] while sending to EPUB via Kindle through amazon
> server. Later I find epubfix.com to solve the langauge encoding error to fix
> the issue.
> **Gemini AI Newsletter:** Utilised the Gemini AI to create a daily AI
> newsletter from the topic contained inside from different csv topics for
> daily micro learning like finance and other stuff and sending some
> motivational stuffs daily morning.
> And finally **readablity.js** which is a best javascript library for json
> fetching for any site provided by reader mode in mozilla firefox browsers I
> got inspired by a paid solution for my problem push-to-kindle by
> fivefilters.org which is best solution for this problem but paid and works
> for only single blog/link. Initially I was doing for scraping different
> content manually by identifying different div classname and elemnt for every
> site but readablity.js can be very helpful by reducing unncessary works best
> to train RAG models too.
> Cloudscaper: Cloudscraper is tool used to bypass cloudflare element.
> And obviously A lot of programming challenges to implement this with python
> with a lots of bugs while facing significant issue with file manipulations.

It was a long journey I feel very engaged and utilised my spare time. Also
thanks GPT for being a great tool for exploring new ideas. I would not have
gone into much depth without these tools and fixing bugs along the way. At end
I realized that I'm working on a 10 years old problem 😃 but never knew about
it until I find different github repo solving almost same problems around it.
But It was fun to initiate and solve and not rely upon paid solution.
Keep learning and exploring. Don't miss to solve such problems which you face
daily life. I'm very happy that Finally I find a way and love the learning it
provided me.

[Visit Github Repo](https://github.com/ajaykrmnc/DailyNews)

## Why ??

---

_I've always felt a deep need to start my mornings with something meaningful.
There was a certain sense of fulfillment missing from my daily life, and I
often found myself immediately scrolling through reels, shorts, or social
media feeds upon waking. To combat this distraction, I purchased a Kindle,
hoping to immerse myself in meaningful reading each morning. However, I soon
discovered a significant amount of friction between the act of opening the
Kindle and actually engaging with a good book. Recognizing this obstacle, I
felt compelled to find a solution._

## What I've Achieved.

- Parsing the TechCrunch, YourStory, DristiIAS Current Affair website.
- Sending Daily one Gita Verse using GeminiAI
- All the The Hindu Editorial through fetching rss feeds and since It requires
  paid subscription I think that was awesome to find away for free 😃.
- Scrapping the Whole blog website of Devdutt Patnaik Mythology Blog Website
  from 2000 to 2025 and scheduling them to send it to my Kindle starting from 9
  June 2025 till my lifetime 😃.

<div style="display: flex; flex-direction: row; justify-content:
  space-between;">
  <img src="attachments/Pasted image 20250612093543.png" style="width: 40%;">
  <img src="attachments/WhatsApp Image 2025-06-19 at 10.05.19 PM.jpeg"
    style="width: 40%;">
</div>

---

Things Need to be Added

- EPUB Cover
  - [x] Change the Cover before converting into the EPUB
  - [ ] Generate Table of Content for the EPUB Generation with different Tag
        Element.
  - [ ] AI based summary of each html file
  - [ ] All Editorial Summaries with AI
  - [ ] Question Answering with AI
  - [ ] Generate a Next/Prev Article Section Tab at the end of each articl
  - [ ] Build a Database for email listing like User's
  - [x] Buid a Calibre recipe and Understanding the Calibre recipe for this
        article for the website which uses Authentication and browser support.
