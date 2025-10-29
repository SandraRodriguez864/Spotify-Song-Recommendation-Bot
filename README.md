# Spotify Song Recommendation Bot

An Android-first automation that discovers and recommends songs on Spotify based on mood, genres, and user-defined rules. It automates in-app navigation, playlist parsing, and track discovery across real devices and emulators. The outcome: continuous, human-like song recommendations and curated shortlists ready to save or export.

<p align="center">
  <a href="https://Appilot.app" target="_blank">
    <img src="media/appilot-baner.png" alt="Appilot Banner" width="100%">
  </a>
</p>
<p align="center">
  <a href="https://t.me/devpilot1" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20Appilot%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:support@appilot.app" target="_blank">
    <img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://appilot.app" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>

<p align="center"> 
   Created by Appilot, built to showcase our approach to Automation!<br>
   <strong>If you are looking for custom Spotify Song Recommendation Bot, you've just found your team — Let’s Chat.👆👆</strong>
</p>

## Introduction
This system automates Spotify song discovery on Android. It opens the Spotify app, searches by mood/genre/keywords, explores related artists/playlists, and compiles fresh recommendations with human-like timing.  
It removes the repetitive grind of manual discovery, surfacing tracks that match defined rules (energy, tempo, release window, popularity bands) while rotating proxies and devices for scale.  
For teams and creators, it provides consistent, scalable music exploration that feeds playlists, content calendars, and listening pipelines.

### Automating Spotify Discovery and Curation
- Navigates Spotify app flows (search → filters → recommendations → related artists → user playlists) with UI Automator/Appium.
- Applies configurable heuristics (tempo/energy window, popularity brackets, “newness bias”) to rank suggestions.
- Learns signals from previous accept/skip actions to refine future recommendations.
- Produces exportable shortlists (CSV/JSON) and optional auto-save to designated playlists.

## Core Features
- **Real Devices and Emulators:** Run on physical Android phones and emulator stacks (Bluestacks/Nox) for realistic app behavior and better anti-detection variance.
- **No-ADB Wireless Automation:** Control devices over Wi-Fi (scrcpy/Appilot bridge) to keep cables out of large farms and reduce ADB fingerprint noise.
- **Mimicking Human Behavior:** Randomized delays, scroll velocities, tap coordinates, backtracks, and occasional “curiosity” branches to emulate authentic exploration.
- **Multiple Accounts Support:** Rotate through many Spotify accounts with isolated device profiles, cookies, and storage partitions.
- **Multi-Device Integration:** Orchestrate 10–300+ devices concurrently with task queues, per-device schedulers, and health checks.
- **Exponential Growth for Your Account:** Compounds discovery cycles to steadily enrich playlists and surface niche gems that improve engagement and retention.
- **Premium Support:** Priority troubleshooting, rule tuning, and device-farm scaling guidance from Appilot engineers.
- **Heuristic Ranking Engine:** Rank candidates by tempo/energy/popularity windows, release recency, and artist diversity constraints.
- **Playlist Mining:** Explore thematic and user-curated playlists; de-duplicate and enforce novelty thresholds.
- **Adaptive Feedback Loop:** Learn from keeps/skips and update weights for genre, BPM, and “similar artist” hops.

| Feature | Description |
| --- | --- |
| **Proxy & Fingerprint Rotation** | Integrates residential/mobile proxies and device-fingerprint variance to lower bot-detection risk. |
| **Schedule & Throttling** | Time-based schedules with per-account caps (daily searches, additions, likes) to preserve trust. |
| **Crash & Retry Logic** | Auto-recovers from app freezes, stale elements, and network hiccups with bounded retries and fallbacks. |
| **Structured Exports** | Output recommendations to `/output/recommendations.csv` and `/output/recommendations.json` with metadata (artist, album, BPM, energy, popularity). |
| **Rule Templates** | Prebuilt rule sets (e.g., “Focus Lo-Fi,” “Gym EDM,” “Fresh Indie 80–120 BPM”) for one-click deployments. |
| **Observability** | Centralized logs, screenshots-on-error, and per-device run summaries for audits and tuning. |

</p>
<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="spotify-song-recommendation-bot-architecture.png" alt="spotify-song-recommendation-bot-architecture" width="95%">
  </a>
</p>

## How It Works (must)
1. **Input or Trigger** — Start from the Appilot dashboard: define seed terms (moods, genres, artists), ranking rules (BPM/energy/popularity), schedule, and device/account pools.  
2. **Core Logic** — Appilot drives Android devices via **UI Automator/Appium/ADB**, opens Spotify, performs searches, explores recommendations/related artists/playlists, and evaluates candidates against rules.  
3. **Output or Action** — Selected tracks are added to a target playlist or exported to CSV/JSON; optional shortlist review before saving.  
4. **Other functionalities** — Automatic retries, structured logging, per-step screenshots, parallel processing, and alerting on anomalies are configurable within the Appilot dashboard.

## Tech Stack (must)
- **Language:** Kotlin, Java, Python, JavaScript  
- **Frameworks:** Appium, UI Automator, Espresso, Robot Framework, Cucumber  
- **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, Bluestacks, Nox Player, Scrcpy, Firebase Test Lab, Accessibility  
- **Infrastructure:** Dockerized device farms, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues, Real device farm

## Directory Structure (must)
```
spotify-song-recommendation-bot/
│
├── src/
│ ├── main.py
│ ├── automation/
│ │ ├── device_controller.py
│ │ ├── spotify_flows.py
│ │ ├── selectors.py
│ │ ├── heuristics.py
│ │ ├── scheduler.py
│ │ └── utils/
│ │ ├── logger.py
│ │ ├── proxy_manager.py
│ │ ├── bpm_energy_estimator.py
│ │ └── config_loader.py
│ └── workers/
│ ├── run_device_worker.py
│ └── orchestrator.py
│
├── config/
│ ├── settings.yaml
│ ├── rules/
│ │ ├── focus_lofi.yaml
│ │ ├── gym_edm.yaml
│ │ └── fresh_indie.yaml
│ └── credentials.env
│
├── logs/
│ ├── device-001.log
│ └── device-aggregate.log
│
├── output/
│ ├── recommendations.csv
│ └── recommendations.json
│
├── tests/
│ ├── test_heuristics.py
│ ├── test_selectors.py
│ └── test_flows.py
│
├── docker/
│ ├── Dockerfile
│ └── docker-compose.yml
│
├── requirements.txt
└── README.md
```

## Use Cases (must)
- **Indie curators** use it to discover niche tracks for daily playlist updates, so they can keep followers engaged without manual digging.  
- **Content creators** use it to feed background music pipelines (mood-bound) for videos, so they can maintain a consistent sonic brand.  
- **Studios/labels** use it to monitor adjacent genres and surface rising artists, so A&R can move faster with data-backed shortlists.  
- **Fitness brands** use it to maintain BPM-aligned workout playlists, so coaches get fresh, on-tempo sets each week.

## FAQs
**How do I configure this automation for multiple accounts?**  
Define each account’s device/profile mapping in `config/settings.yaml`. The scheduler rotates accounts with per-day limits to keep flows human-like.

**Does it support proxy rotation or anti-detection?**  
Yes. Residential/mobile proxies can be assigned per device. The system randomizes tap timing, scroll patterns, and navigation depth to reduce detection signals.

**Can I schedule it to run periodically?**  
Absolutely. Use the scheduler to set daily/weekly runs with task caps (searches, additions) and auto-pause windows.

**Can I control recommendation rules (BPM/energy/recency)?**  
Yes. Edit rule templates in `config/rules/*.yaml` or create your own with BPM/energy/popularity windows and release recency constraints.

**What if the app crashes or UI changes?**  
Crash/timeout detectors trigger retries and fallback selectors. You’ll get logs and screenshots to retrain selectors when Spotify updates UI.

## Performance & Reliability Benchmarks (must)
- **Execution Speed:** Processes ~100–150 actions/minute per device (searches, scrolls, evaluations) with async I/O and cached selectors.  
- **Success Rate:** Maintains a 95%+ stable run rate across discovery cycles with bounded retries.  
- **Scalability:** Proven orchestration across 300–1,000 Android instances using parallel device workers and queue-based scheduling.  
- **Resource Efficiency:** Lightweight workers (~200–300MB RAM/device) with log-level tuning and lazy-loading of heavy modules.  
- **Error Handling:** Exponential backoff, circuit breakers per device, structured logs,

##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>
