# V2Ray Config Mirror

A size-capped mirror of [ebrasha/free-v2ray-public-list](https://github.com/ebrasha/free-v2ray-public-list) — automatically synced every 30 minutes via GitHub Actions.

Each config file is independently capped, so the total repo stays within your desired size budget.

## How to Use

Raw config URLs from this repo (same filenames as source):

```
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/V2Ray-Config-By-EbraSha-All-Type.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/all_extracted_configs.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/vless_configs.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/trojan_configs.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/vmess_configs.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/ss_configs.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/V2Ray-Config-By-EbraSha.txt
https://raw.githubusercontent.com/YOUR_USER/YOUR_REPO/main/ssr_configs.txt
```

Replace `YOUR_USER` and `YOUR_REPO` with your GitHub username and repo name.

## Configuration

All settings are in `.github/workflows/fetch.yml`:

| Setting | Location in file | Description |
|---------|-----------------|-------------|
| `MAX_SIZE_MB` | `env:` block | Per-file size cap in MB (default: `10`) |
| Cron schedule | `on.schedule.cron` | Run cadence (default: `*/30 * * * *`) |

Edit these values and push to `main` — the next run uses the new settings.

## How It Works

1. A GitHub Actions workflow runs on your configured schedule
2. It downloads each config file from the source repo, truncated to `MAX_SIZE_MB`
3. Files are committed as a single squashed commit and force-pushed (no history kept)
4. The repo always contains exactly one commit — the current snapshot

## Requirements

- A **private** GitHub repository (Actions on private repos: 3,000 free minutes/month)
- At 30-minute intervals you use ~1,440 min/month — well within the free tier

## License

Same as the source: the configs are publicly shared data. This repo is purely a mirror.
