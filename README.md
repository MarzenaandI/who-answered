# Who actually answered? · Kto naprawdę odpowiadał?

**EN** · A single HTML page that reads your ChatGPT data export and shows which model actually wrote each reply.
Every reply in the export carries a hidden field, `model_slug`. This page counts how often a model other than GPT‑4o answered inside conversations that were running on GPT‑4o.

**PL** · Jedna strona HTML, która czyta Twój eksport danych z ChatGPT i pokazuje, który model naprawdę napisał każdą odpowiedź.
Każda odpowiedź w eksporcie ma ukryte pole `model_slug`. Strona liczy, jak często w rozmowach prowadzonych na GPT‑4o odpowiadał inny model.

## Use it · Jak użyć

1. ChatGPT → Settings → Data controls → **Export data**. Wait for the e‑mail, download the zip.
2. Unzip it. Find `conversations.json` (older exports) or `conversations-000.json …` (newer exports).
3. Open the page and drop the file(s) or the whole unzipped folder on it.

Online: **https://marzenaandi.github.io/who-answered/**
Offline: download `index.html` and open it in any browser. It works the same.

## Privacy · Prywatność

🔒 **Nothing leaves the tab.** The files are read by your browser and never uploaded anywhere. Close the tab and it is gone.
🔒 **Nic nie opuszcza karty.** Pliki czyta Twoja przeglądarka i nigdzie ich nie wysyła. Zamkniesz kartę i wszystko znika.

The shareable summary contains monthly counts only, no titles, no message text, no IDs, unless you tick the box to include thread titles.

## What it shows and what it does not · Co pokazuje, a czego nie

- A "4o thread" is a conversation whose default model was GPT‑4o, or where most replies came from GPT‑4o.
- `gpt-5*` / `gpt-6*` replies inside a 4o thread are the clearest sign of re‑routing.
- `gpt-4o-mini` / `gpt-4.1-mini` is usually the usage cap, not content.
- Replies after a tool you switched on yourself (Deep Research, search) are counted separately, not treated as a swap.
- The export records **which model wrote a reply, not who decided it**. It cannot tell a router from a click. If you never switched models by hand, say so when you share.
- Only the visible branch of each conversation is counted; edited or regenerated branches are skipped.
- Share everything you find, including GPT‑4o replies you think were harmful. A summary trimmed to fit a thesis is easy to dismiss.

## Credits

Made by Marzena Nehrebecka with Claude (Opus 5.5). No tracking, no analytics, no server.
