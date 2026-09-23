# Tool-Translate-Updates

Every copy of **Video Voice Translator** reads `latest.json` from here when it
opens. Nothing else is in this repo, on purpose: it is public so the app can
read it without a password, and the app's own code stays private elsewhere.

## Download

**https://github.com/Nimithh/Tool-Translate-Updates/releases/latest/download/VideoVoiceTranslator.zip**

This link always gives the newest version, so it can be sent once and kept.
The zip holds the exe and READ-ME-FIRST.txt in one folder. The app will not
run without a licence code, so a public download gives nothing away.

## Releasing a new version

1. In the app's code, raise `APP_VERSION` in `backend/utils/version.py`
   — for example `1.0.0` to `1.1.0` — and build.
2. Make a new Release here (Releases → Draft a new release), tag it with
   the version — `v1.1.0` — and attach the zip. **Name the file exactly
   `VideoVoiceTranslator.zip`**, or the download link above stops finding it.
3. Here, edit `latest.json` and raise `"version"` to match.

Anyone still on an older version sees, the next time they open the app:

> Version 1.1.0 is ready. Message @chhannnimith on Telegram to get it.

They keep working; it is only a notice. Put a short line in `notes_en` /
`notes_km` and it is shown after the message.

## The fields

| field | what it does |
|---|---|
| `version` | the newest version. Anyone below it sees the notice. |
| `minimum` | anyone **below this cannot use the app** — it tells them to update, then closes. |
| `contact` | shown in the message: who to ask for the new version |
| `notes_km`, `notes_en` | one line on what is new, per language |

## Be careful with `minimum`

Leave it at `"0"` unless old copies are genuinely broken — for example a
translator or voice service changed and every old build fails. Set it too
high by mistake and every customer who has not updated, paying ones
included, is locked out until they get the new exe.

## If this file cannot be read

The app shows nothing at all and carries on. It never tells a customer
something is wrong because this check failed.
