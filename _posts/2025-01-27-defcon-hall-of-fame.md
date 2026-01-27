---
title: "First to Crack the Defcon Toronto Website CTF: Hall of Fame Entry Secured"
date: 2026-01-27 04:30:00 -0500
categories: [Blog]
tags: [ctf, defcon-toronto, hall-of-fame]
---

# CTF Speed Run to Hall of Fame

Picture this: January 15, 2026. I'm at my first-ever Defcon Toronto (DC416) meetup, soaking in vibes, free pizza, and Tammy Harper from Flare dropping absolute gems on ransomware affiliate life in "Syndicate: Inside the life of a Ransomware operator." Talk was fire, crowd was chill, Toronto cybersecurity scene hitting different.

Then near the end the organizers casually drop: "Yo there's a lil web CTF thingy on our site (https://defcontoronto.ca/), type stuff in the homepage terminal. First solvers get immortalized in the hall of fame right there in the terminal lmao."
Challenge accepted.

![Defcon Toronto Event](/assets\img\defcon_toronto1.png)

*Me blending in like a true introvert*

Got home, cracked a white monster, and dove in. **SPOLIER ALERT:** Got first blood and my name (gr3ysec) is now in the hall of fame.

![Hall of Fame](/assets/img/hall_of_fame.png)

The terminal on the homepage asks for a password when you type "sudo". To solve it, I started by viewing the page source. HTML spilling tea, event deets, hidden SoundCloud banger, Discord link... but no obvious password. Tried "syndicate", "ransomware", "flare", "tammyharper". All Ls, skill issue. Then noticed the terminal is an iframe src="https://dc416-terminal.pages.dev/".

![Page Source Screenshot](/assets\img\dc416_page_source.png)  
*(Looking through the HTML for any hints or useful strings)*

I inspected the frame source and saw it loads a JavaScript file at /assets/index-nyRa8SHu.js. In that script, the sudo password was defined plainly as "DC416isback". Password literally hardcoded in the JS like it's 2005

![Captured flag](/assets\img\dc416isback.png)
*(Me when I saw "DC416isback" chilling in plain text: 😭💀)*

Typed sudo, pasted "DC416isback", hit enter, "**PERMISSION GRANTED. Try rm -rf**"
Bro. They really gave the nuclear option.

![password granted](/assets\img\granted.png)
*Access granted, feeling like Mr. Robot for 0.2 seconds*

Immediately rm -rf src because why not commit digital war crimes in a safe space?
Terminal glitches out HARD: black background, pixel font activated, messages pop up:
"What made you think that was a good idea?"
"Now everything is ruined."
I broke it. I actually broke the terminal.

![ruined state](/assets\img\ruined1.png)  
*Ruined mode activated. Terminal looking like it just got ratio'd by reality*

Tried help: "maybe restarting your browser will fix this" (savage).
whoami: "visitor" (still unemployed in sim).
ls: empty (skill issue).
sudo: "no." (fair).

**TL;DR speedrun recap:**  

Meetup > heard about CTF > stayed up like a goblin > inspected iframe JS > found "DC416isback" > sudo > rm -rf src > terminal self-destruct sequence > hall of fame first entry secured.

Shoutout to the DC416 crew for the tough CTF. Toronto cyber fam is actually wholesome, join the Discord or hit the next Meetup if you're around.