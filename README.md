# Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook

Turn any public **Instagram Reel, TikTok video or Facebook video/Reel** into text with **one Actor for the three networks**: the full transcript, timestamped sentences, the spoken language, the **first-3-seconds hook**, the video details, and, if you want, the **same transcript translated into up to 30 languages with the same timestamps** (SRT/VTT) and the **comments** of each video. Paste one link or thousands, mixing platforms freely.

**[Run it on Apify](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)**: no install, no login, free credit on a new Apify account.

## What you get

- **Three networks, one input, one price**: Instagram Reels, TikTok and Facebook videos in the same list, no separate Actor per network
- **Full transcript text**, ready for search, summaries, translation, content research or LLM pipelines
- **Timestamped segments** (start, end, text) for subtitles, clipping or chapters
- **Hook**: the sentences that start in the first 3 seconds, the part that decides if people keep watching
- **Language detection** in 50+ languages (or force one, e.g. `pt`, `es`, `hi`)
- **Video details at no extra cost**: author, duration, upload date, views, likes, comment count, caption, thumbnail
- **Clear status per video**: `ok`, `no_speech`, `not_video`, `private_or_login`, `unavailable`, `too_long`, `invalid_url` or `blocked`
- **TikTok's own captions when they exist** (`source: platform_captions`), always the original spoken language (never TikTok's machine translation); otherwise speech-to-text (`source: speech_to_text`)
- **Translations with the same timestamps** (`translateTo`): get the transcript in up to 30 other languages, for Instagram, TikTok and Facebook, plus SRT or WebVTT subtitle files (`subtitleFormat`). $0.002 per extra language

## Pricing

**You pay only for transcripts delivered: $0.01 per video** (covers up to 90 seconds of speech-to-text audio; longer videos add $0.008 per extra minute). Videos with no speech (music only), photos, private or deleted posts and invalid links are listed in the results with the reason, and are **never charged**.

That is the free-plan price; Apify paid plans (Bronze, Silver, Gold) pay less per item.

## Call it by API

```bash
curl -X POST "https://api.apify.com/v2/acts/pomlabs~social-video-transcript/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"urls": ["https://www.instagram.com/reel/DFFyRp-pINJ/", "https://www.tiktok.com/@.saudetop/video/7341012983058812165"]}'
```

Python:

```python
from apify_client import ApifyClient

client = ApifyClient("YOUR_APIFY_TOKEN")
run = client.actor("pomlabs/social-video-transcript").call(run_input={"urls": ["https://www.instagram.com/reel/DFFyRp-pINJ/", "https://www.tiktok.com/@.saudetop/video/7341012983058812165"]})
for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item)
```

## Use it from Claude, Cursor or any MCP client

```bash
claude mcp add social-video-transcript "https://mcp.apify.com?tools=pomlabs/social-video-transcript" -t http
```

## Ready-made examples

- [Instagram Reel transcript generator (with the hook)](https://apify.com/pomlabs/social-video-transcript/examples/instagram-reel-transcript-with-hook)
- [Transcribe a TikTok video to text](https://apify.com/pomlabs/social-video-transcript/examples/tiktok-transcript-to-text)
- [Transcribe a Facebook video and translate it](https://apify.com/pomlabs/social-video-transcript/examples/facebook-video-transcript-translated)

## More Actors by Pom Labs

- [YouTube Transcript Scraper: Translate, No Login · $3/1K](https://apify.com/pomlabs/youtube-transcript-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Reddit Scraper: Deleted & Removed, Mods, Hidden Profiles](https://apify.com/pomlabs/reddit-posts-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [LinkedIn Company Scraper (No Cookies): Posts, Similar Companies](https://apify.com/pomlabs/linkedin-company-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [YouTube Comments Scraper + Replies, Shorts · No API Key · $1/1K](https://apify.com/pomlabs/youtube-comments-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Instagram Profile Scraper: Exact Followers, Reels Views](https://apify.com/pomlabs/instagram-profile-data?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [LinkedIn Profile Scraper (No Cookies) + Similar Profiles](https://apify.com/pomlabs/linkedin-profile-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Threads Scraper: Keyword Search, Posts & Profiles · No Login](https://apify.com/pomlabs/threads-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [AliExpress Scraper: Exact Units Sold, Prices, Search · $1/1K](https://apify.com/pomlabs/aliexpress-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [AI Brand Visibility Tracker - ChatGPT, Claude & Perplexity](https://apify.com/pomlabs/ai-brand-visibility?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Mercado Livre & Amazon BR Coupon Code Checker](https://apify.com/pomlabs/mercadolivre-coupon-checker?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Page Time Machine · Wayback Diff + AI · No Login · $2.5/1K](https://apify.com/pomlabs/page-time-machine?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Video Downloader: TikTok No Watermark, Instagram, YouTube, X](https://apify.com/pomlabs/video-downloader?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [NSFW Image Detector & Image Tagger - Moderation + Categories](https://apify.com/pomlabs/image-moderation-tagger?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)
- [Google Trends Scraper: Related Queries, No 429 · $2/1K](https://apify.com/pomlabs/google-trends-scraper?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript)

Full documentation, input fields and output format: [Instagram Transcript Scraper: Reels, TikTok, Facebook, Hook on Apify](https://apify.com/pomlabs/social-video-transcript?utm_source=github&utm_medium=readme&utm_campaign=social-video-transcript).
