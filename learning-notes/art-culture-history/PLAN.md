# Art & Culture History - Episode Intake Plan

Goal
- Build a steady stream of one In Our Time episode per day (or closest available) to populate a daily note in Obsidian.
- Assemble key metadata automatically: title, pubDate, description, link, duration, enclosure URL.
- Store notes in a consistent format in this vault folder.

Workflow
1) Fetch the RSS feed(s) for In Our Time:
   - Primary feed: https://feeds.bbci.co.uk/programmes/b006qykl/episodes/rss.xml
   - Backup feed (backup): http://downloads.bbc.co.uk/podcasts/radio4/iot/rss.xml
2) Parse latest episodes in order of publication date.
3) Create one Obsidian note per day:
   - Path: Art & Culture History/YYYY-MM-DD.md
   - Contents include: title, date, summary, links, and a short notes section for personal insights.
4) Link each daily note to the source episode via a standard header and include a “Plan for next” blurb.

Data fields to capture
- Episode Title
- Publication Date
- Description (short)
- Link (episode page)
- Enclosure URL (audio)
- Duration (seconds)
- Source Feed name
- Personal notes (for reflections)

Note structure example

---
YYYY-MM-DD: The Roman Arena
Title: The Roman Arena
PubDate: Thu, 26 Feb 2026 10:15:00 +0000
Source: BBC Radio 4 - In Our Time
Link: http://www.bbc.co.uk/programmes/b006qykl
Enclosure: http://open.live.bbc.co.uk/mediaselector/6/redir/version/2.0/mediaset/audio-nondrm-download-rss/proto/http/vpid/p0mw2pfd.mp3
Duration: 3484
Notes: Initial log for this episode. 
---

First concrete sample (for reference)
- Title: The Roman Arena
- PubDate: Thu, 26 Feb 2026 10:15:00 +0000
- Link: http://www.bbc.co.uk/programmes/m002qj85
- Enclosure: http://open.live.bbc.co.uk/mediaselector/6/redir/version/2.0/mediaset/audio-nondrm-download-rss/proto/http/vpid/p0mw2pfd.mp3
- Duration: 3484

How I’ll run this
- Daily automatic fetch at 10:00 local time (Europe/Berlin)
- Wake-trigger possibility: try to run on startup when OpenClaw initializes
- Backups: store in backup subfolder daily as well

Notes
- This note is auto-generated for planning. You can edit to add your own insights.
