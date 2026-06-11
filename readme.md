# Github Auto Committer

Automatically makes random daily commits to keep your GitHub contribution graph active using GitHub Actions.

## How it works

- Runs every day at **9:00 AM UTC** via GitHub Actions
- Makes a **random number of commits** (default: 10–32) per day
- Updates `last_active.txt` with timestamp on each commit
- All commits appear on your GitHub contribution graph

## Setup

### 1. Fork this repo

### 2. Enable workflow permissions

**Settings → Actions → General → Workflow permissions → Read and write permissions**

### 3. Add required secrets

**Settings → Secrets and variables → Actions → New secret**

| Secret       | Value                                                                   |
| ------------ | ----------------------------------------------------------------------- |
| `USER_EMAIL` | Your GitHub noreply email `123456789+username@users.noreply.github.com` |
| `USER_NAME`  | Your GitHub username                                                    |

> Find your noreply email at **GitHub → Settings → Emails → Keep my email address private** (or you just enter your github email)

### 4. Test manually

**Actions tab → Daily Auto Committer → Run workflow**

## Change commit range

Edit these two lines in `.github/workflows/daily-commit.yml`:

```bash
MIN=10
MAX=32
```

## Change schedule

Edit the cron line in `.github/workflows/daily-commit.yml`:

```yaml
- cron: "0 9 * * *" # Every day at 9:00 AM UTC
```

Use [crontab.guru](https://crontab.guru) to generate your preferred schedule.

## Stop / Pause

**Actions tab → Daily Auto Committer → ⋯ (3 horizontal dot button) → Disable workflow**

Re-enable anytime from the same place.

## ⚠️ Important

- Use your **noreply email** not your real email - protects your privacy
- Both secrets are **required** - workflow will fail without them
- Works only if repo is **public** for unlimited free Actions minutes
- **Don't forget to star the repo**
