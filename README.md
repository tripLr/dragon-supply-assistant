# Dragon Supply Assistant

A click-to-run AI helper bot that writes a **weekly local-resource notification draft for each person you help** — for example, people on disability or a fixed income who can't easily shop around.

Every week the bot checks local store ads and free food giveaways near each person and writes one short email draft per person. **It never sends anything.** A human volunteer reviews every draft, fixes anything wrong, and sends it themselves.

> Status: **beta**. A one-click template link (so anyone can get their own copy of the bot) is coming after the beta weeks. Until then, use the setup steps below.

## What each weekly draft covers

- **Food deals ranked by protein per dollar** — eggs, beans, chicken, peanut butter, canned fish, etc., from the current weekly ad only.
- **Real produce** — fresh or plain canned/frozen fruit and vegetables on sale (not snack foods).
- **Pet supplies** — only if the person has pets.
- **No-shop / car items** — things that keep without a fridge or can ride in a car, for people who can't make frequent trips.
- **Free giveaways** — food bank pantries, mobile pantries and community distributions, each with **date, place, hours and phone number**.
- **Delivery note** — a one-line "is delivery worth it this week?" note, comparing store curbside/pickup to delivery-app markups and fees.
- **Only what's new** — after the first week, the draft lists only what's new or better than last week, or says "no change".

## How it works

1. You keep a simple sheet of the people you help (see `templates/supply-list-template.csv`).
2. On a schedule (e.g. every Tuesday morning), the bot reads the sheet and the rules in `prompts/weekly-instructions.md`.
3. For each person it researches their town's store ads and giveaways, then creates **one email draft per person** in your mail account.
4. You review and send. A running log records what was in each week's draft so next week only adds what changed.

## Setup (beta)

1. **Copy the sheet template.** Import `templates/supply-list-template.csv` into Google Sheets (or any spreadsheet). Add one row per person, with their permission. Keep this sheet private — it never goes in this repo.
2. **Create your bot.** In an AI agent app that can read a sheet, search the web and create email drafts (the beta runs on Grok Bot), create a new bot and paste in `prompts/weekly-instructions.md` as its instructions.
3. **Point it at your sheet and mail.** Give the bot the link to your private sheet and connect your email account **with draft access only** in your workflow (the rules forbid sending).
4. **Schedule it.** Set a weekly run (for example, Tuesday 8 AM local time). Optionally add a short weekday check for giveaways happening the next day.
5. **Review every draft.** Check prices, hours and phone numbers, then send it yourself.

See `examples/sample-email.md` for what a draft looks like (made-up example data).

## Privacy

- No real person's name, email, address or phone number belongs in this repo. Keep your list in your own private account.
- Only help people who have agreed to receive these emails.

## Safety rules (short version)

Drafts only. Never send, never order, never sign anyone up for benefits. Never invent people, prices or events. Every giveaway needs a date and address, and hours should be confirmed. Full rules: `prompts/weekly-instructions.md`.

## License

MIT — free for anyone to copy, use and adapt. See `LICENSE`.
