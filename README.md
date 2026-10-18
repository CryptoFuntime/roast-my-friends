# Roast My Friends — Roast Cards Beta

Mobile-first static web app. Open `index.html` in a browser or deploy the folder to a static host.

## Features
- Personalized joke templates with three intensity levels and three comedy personalities
- Neon, Trading, and Wanted poster-style cards
- Download PNG card, native share on supported browsers
- Collect up to 30 cards in local browser storage
- No API keys, accounts, tracking, or server costs

## Limitations
This is a browser-only beta. Jokes use built-in templates rather than AI. Collection data stays on the current device/browser. No cloud accounts, payment, or moderation backend. Image text may overflow on unusually long input; preview before sharing.

## Next steps
Deploy as static site, test with real users, then add authenticated accounts, server-side AI generation, rate limits and abuse controls, and payments only after validation.

## After Dark
Added opt-in 18+ Fucking Nuclear intensity and original comedy personalities (Dirty Mouth, Backwoods Philosopher, Roast Assassin). Explicit language is permitted; hateful and threatening content is not. This remains a local template-based prototype, not live AI.

## AI integration (prepared, not deployed)
`worker/index.js` is a Cloudflare Worker that calls the OpenAI Responses API with a secret key. It validates inputs, constrains comedy styles, and restricts browser access to a configured origin. Set `OPENAI_API_KEY` as a Worker secret and `ALLOWED_ORIGIN` to the exact deployed website origin. Deploy the Worker, then set the HTML `<meta name="roast-api" content="">` to the Worker endpoint. Until configured, the website runs its original no-cost joke templates. **Do not publish the AI endpoint without implementing server-side rate limits and cost caps**; CORS is not authentication. No AI key belongs in HTML or GitHub source.


## Version 5: Roast Card Studio

- Major responsive dark/neon interface refresh.
- Six comedian-named inspiration selectors (Andrew Dice Clay, Theo Von, Tony Hinchcliffe, Bill Burr, Nikki Glaser, Dave Chappelle), plus original presets. These generate original material based on broad comedy genres, not imitations or endorsements.
- Local fallback jokes and backend prompt mappings added for all six.
- Opt-in 18+ Nuclear intensity retained.
- Deployment and API configuration still required for live AI. Do not publish an API key in index.html.


## Comedy Underground (v6)
Three independent, original challenge presets: Roast Battle, One-Minute Roast and rotating Daily Challenge. Challenge selection is embedded in generated collectible card metadata and sent to the optional AI endpoint. No third-party festival branding, assets, affiliation or endorsement. No public leaderboard or multi-user backend is claimed.

## Version 7
Comedian selector now exclusively lists 17 real comedians, grouped into Living Comedians and Comedy Legends. Fallback and API validation updated. Comedy inspirations are broad genres, not impersonations or endorsements.


## Version 10: Manga Arcade UI
Neon manga styling, responsive illustrated emoji avatar tiles for the real comedian selection, enhanced card framing. These are symbolic emoji placeholders, not licensed photos or likenesses. Live AI and deployment remain pending.


## Version 11: Illustrated comedian gallery
- 17 original local SVG comic portraits in assets/comedians; no remote image dependencies.
- The portraits are stylized illustrations, not accurate photos or authorized likenesses.
- Accessible image labels and responsive gallery improvements.
- Live AI and hosting remain unconfigured.


## Version 12: Roast Call preview
Adds an opt-in, text-only preview of Legends From Beyond. No real calls, audio synthesis, or celebrity voice cloning. Future production calling requires recipient verification, consent, opt-out, abuse prevention, and licensed voices.


## Version 13: Audio preview
- Added Play and Stop buttons to the Legends From Beyond preview.
- Uses the browser's built-in speech synthesis, with a generic device voice and spoken AI disclosure. No paid service, phone numbers, voice cloning, outbound calling or backend required.
- Voice availability varies by browser and iPhone settings; this is not a telephony feature.
- Recipient consent checkbox remains required. Production calling would require verified opt-in and compliance review.


## Version 14 — iPhone installable web app
- Added web app manifest, icon, and offline caching for static app files.
- After hosting over HTTPS, Safari users can use Share → Add to Home Screen.
- Offline mode supports built-in joke templates, saved cards, and device voice where supported. Live AI requires internet and a separately deployed backend.
- Deployment: upload the **contents** of this folder to a static web host (e.g. Cloudflare Pages or Netlify). The worker/ directory is backend source and is not activated by static hosting.
- Never expose an OpenAI API key in frontend code. Before enabling live AI, implement authentication or other robust abuse controls, rate limits, and spending caps.
- This is not yet a real calling product. Audio uses the device voice and recipient opt-in is a checkbox only, not verified consent.
- This build has not been visually tested on an iPhone or deployed.
