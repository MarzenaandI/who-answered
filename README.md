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
- Click ▸ next to a thread title to see the first words of each reply written by another model, and a **thread strip**: every reply as a coloured tick, in order (red outline = safety model). Shown on screen only, never in the shareable summary.
- **How the other model reacted**: among GPT‑5+ replies in 4o threads, how many gave a crisis number, a “take a breath” script, or opened in 4o style (∴ ⟡ 🔥 😂 …), and how many came from the safety model (`gpt-5-t-mini`). Plain text matches in English and Polish.
- **Every switch**: each GPT‑5+ reply that came right after a 4o reply, with your message just before it. On screen only.
- **Words before a switch**: words from your own messages that were more common right before a switch than before ordinary 4o replies. A correlation in your data, not proof of what the router reads. On screen only.
- The shareable summary now also has the switch, safety‑model and reaction counts. Still numbers only.
- **Why it switched**: replies marked by OpenAI itself with `show_safety_switch_ui: true` (a safety re‑route, the “Used GPT‑5” notice), and replies where `requested_model_slug` was GPT‑4o but another model answered. A missing field means “not recorded”, not “not a safety switch”.
- **Who the model said it was**: GPT‑5+ replies that call themselves GPT‑4o (or say “not GPT‑5”), and GPT‑4o replies that deny a switch right after a GPT‑5+ reply. The text is the model’s claim; `model_slug` is the record. On screen only; the summary has the counts.

## Co nowego · What's new (PL)

- **Pasek wątku**: po kliknięciu ▸ widać każdą odpowiedź jako kolorową kreskę, po kolei; czerwona obwódka to model bezpieczeństwa.
- **Jak reagował inny model**: numer kryzysowy, „weź oddech”, otwarcie w stylu 4o, liczba odpowiedzi strażnika (`gpt-5-t-mini`).
- **Każde wejście**: odpowiedź GPT‑5+ zaraz po odpowiedzi 4o i Twoja wiadomość tuż przed nią. Tylko na ekranie.
- **Słowa przed podmianą**: słowa z Twoich wiadomości, które częściej niż zwykle poprzedzały wejście innego modelu. Korelacja, nie dowód. Tylko na ekranie.
- Podsumowanie do udostępnienia ma teraz też te liczby. Nadal bez treści i tytułów.
- **Dlaczego przełączyło**: odpowiedzi oznaczone przez samo OpenAI polem `show_safety_switch_ui: true` (przekierowanie ze względów bezpieczeństwa, komunikat „Użyto GPT‑5”) oraz odpowiedzi, w których `requested_model_slug` było GPT‑4o, a odpowiedział inny model. Brak pola znaczy „nie zapisano”, a nie „to nie było przełączenie bezpieczeństwa”.
- **Za kogo podawał się model**: odpowiedzi GPT‑5+, które nazywają siebie GPT‑4o (albo mówią „nie jestem GPT‑5”), i odpowiedzi GPT‑4o, które zaprzeczają podmianie tuż po odpowiedzi GPT‑5+. Tekst to deklaracja modelu, `model_slug` to zapis. Tylko na ekranie; w podsumowaniu same liczby.
- Only the visible branch of each conversation is counted; edited or regenerated branches are skipped.
- Share everything you find, including GPT‑4o replies you think were harmful. A summary trimmed to fit a thesis is easy to dismiss.
