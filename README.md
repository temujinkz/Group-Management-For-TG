# Group Management for Telegram

A feature‑rich Telegram bot for managing groups at scale. Anti‑flood, anti‑raid, blacklists, federations, custom filters, captcha, scheduled jobs, multi‑language, admin tools, and dozens of moderation modules. Built in Python on top of Pyrogram with MongoDB, Redis, and PostgreSQL for persistence.

## Highlights

- **Moderation:** bans, mutes, warns, kicks, purges, global bans, federations
- **Anti‑abuse:** anti‑flood, anti‑raid, anti‑channel, blacklists (users, words, stickers), force‑subscribe
- **Group ops:** welcome, captcha, approvals, locks, night mode, pin, invite‑link tools
- **Utilities:** notes, custom filters, AFK, info lookups, Google Translate, formatting/fonts, karma
- **Operator tools:** logging channel, debug, eval, dev cmds, backups, DB cleanup, error handling, cron jobs
- **i18n:** multi‑language strings under `Hemal/langs`
- **Pluggable modules:** every feature is its own module under `Hemal/modules` for easy enable/disable

## Stack

| | |
|---|---|
| Language | Python 3 |
| Bot framework | Pyrogram (Telegram MTProto) |
| Datastores | MongoDB, Redis, PostgreSQL |
| Deploy targets | Docker, Heroku, Okteto |

## Configuration

Copy `sample.env` to `.env` and fill in:

```bash
API_ID=               # from my.telegram.org
API_HASH=
TOKEN=                # bot token from @BotFather
OWNER_ID=             # your Telegram user id
OWNER_USERNAME=
SUPPORT_CHAT=
LOGGER_ID=            # private channel id for logs
DEV_USERS=
MONGO_DB_URI=
DATABASE_URL=         # PostgreSQL
```

## Run

**Local**
```bash
pip install -r requirements.txt
python -m Hemal
```

**Docker**
```bash
docker compose up --build
```

**Heroku**
The repo includes `Procfile`, `app.json`, `Aptfile`, `runtime.txt`, and `heroku.yml`. One‑click deploy via Heroku, or `git push heroku main`.

**Okteto**
`okteto-pipeline.yml` configures Okteto cloud builds.

## Structure

```
Hemal/
  __main__.py           entry point
  modules/              every feature is a module
  helper_funcs/         shared helpers
  utils/                utility helpers
  langs/                i18n strings
  no_sql/               MongoDB layer
config.py               env-driven Config / Production / Development
requirements.txt
Dockerfile, docker-compose.yml
Procfile, app.json, heroku.yml, Aptfile, runtime.txt
okteto-pipeline.yml
```

## License

See `LICENSE`.
