---
{"dg-publish":true,"permalink":"/coding/linux-system-programming/daily-digest-to-kindle/","dgPassFrontmatter":true,"noteIcon":"","created":"2025-06-09T12:53:56.738+05:30","updated":"2025-06-11T18:00:43.052+05:30"}
---

Hello everyone. 
I just wanted to share something beautiful thing I've realised that feels good about learning computer and programming stuff I how fulfilling it is to apply my programming knowledge to a real problem I genuinely wanted to solve.

The problem is really very simple: To  daily send tech/finance/national news  & some article from different sites to my e-ink device Kindle in epub format without opening my laptop or doing it manually. \[FYI] the only way to send file to Kindle Device is via kindle email.

But it opens a complet e new whole lot of learning along the way. I am listing all the cool stuffs learnt iteratively on this way. 

> [!Note]
> **Calibre** - A famous ebook software management tools and its cli tools like ebook-convert(converting html or .md to epub) and calibre-smtp(sending a mail). Also I discovered Kovid Goyal brain behind Calibre.
> **SMTP server**: We can set the gmail SMTP server to send one email to another email by assigning a port on a sever and using our gmail app password.
> **Cron Job & Github Actions:** Cron Job: A .yml file for automating repeated job daily  Great for automating cron job daily without manual job for opening laptop daily connecting to the internet and visiting for every site.
> **Web-srcapping**: Scrapped a whole blog website and save it to the .csv file all the important blog links associated to it.
> **HTML-parsing** : Learnt on the way how to parse different sites using dom manipulation and querying for different element for different sites
> **Tamper-monkey**: \[ A Chrome extension] Initially I thought tampermonkey will help in webparsing by visiting website and manipulating the dom element on the browser. It helps automatically when a sites loads it can remove all the unnecessary content on any website like ads, side menus. 
> **Python Library like BeautifulSoup**: Then I learnt a better way by using beautifulSoup and using python library like requests
> RSS Feeds: Intially I throught different links can be fetched by web-parsing but later I realized that the recent blogs and updated content of the website are managed through the RSS Feeds. 
> **Epub Formatting** : Yes a lot of learning also involved how epub file is created and how to format which suits for Kindle. Also I faced a lot of error E999 \[Internal Error] while sending to EPUB via Kindle through amazon server. Later I find epubfix.com to solve the langauge encoding error to fix the issue.
> **Gemini AI Newsletter:** Utilised the Gemini AI to create a daily AI newsletter from the topic contained inside from different csv topics for daily micro learning like finance and other stuff and sending some motivational stuffs daily morning.
> And finally readablity.js which is a best javascript library for json fetching for any site provided by reader mode in mozilla firefox browsers I got inspired by a paid solution for my problem push-to-kindle by fivefilters.org which is best solution for this problem but paid and works for only single blog/link. Initially I was doing for scraping different content manually by identifying different div classname and elemnt for every site but readablity.js can be very helpful by reducing unncessary works best to train RAG models too.
> And obviously A lot of programming challenges to implement this with python with a lots of bugs while facing significant issue with file manipulations.

It was a long journey I feel very engaged and utilised my spare time. Also thanks GPT for being a great tool for exploring new ideas. I would not have gone into much depth without these tools and fixing bugs along the way. At end I realized that I'm working on a 10 years old problem 😃 but never knew about it until I find different github repo solving the problems around it. But It was fun.
Keep learning and exploring. Don't miss to solve such problems which you face daily life. I'm very happy that Finally I find a way and love the learning it provided me.


## Why ??
***
So I was always feel that when I woke up in the morning I wanted to something meaningful. Somewhere It was missing in my daily life and I get started with scrolling the reel or shorts or opening the social media. To avoid or cut this distraction I bought up a kindle to read something meaningful in the morning. But late I found that the there is so much friction from opening a kindle to reading a good book on Kindle. To eliminate this issue I was very compelled to solve this issue. 
