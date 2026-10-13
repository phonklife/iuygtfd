# Instrukcje dla Copilota — phonklife/iuygtfd

## Fakty o repo
- Jedyne źródło kodu: `generator.py`. Tworzy `archive/` (notatki Obsidian + canvas) i `site/` (strona).
- `site/` buduje CI (`.github/workflows/static.yml`) przy każdym pushu do `main` i publikuje na GitHub Pages. `site/` jest w `.gitignore`.
- `archive/` i `index.html` są commitowane. `index.html` w katalogu głównym to kopia `site/index.html`.
- Dane utworów: lista `VIRTUALLUSER_TRACKS` w `generator.py`. Obecne 10 utworów to placeholdery — ich ID nie istnieją w Suno.
- Linki `cdn1.suno.ai/<id>.mp3` nie działają (CDN wymaga podpisanego linku). Działa odtwarzacz osadzony `https://suno.com/embed/<id>` dla prawdziwych ID.
- Adresy repo i strony: stałe `REPO_URL` i `PAGES_URL` w `generator.py`. Nie wpisuj adresów na sztywno.

## Po każdej zmianie w `generator.py`
1. `python3 generator.py` kończy się bez błędu.
2. `cp site/index.html index.html`
3. Commit: `generator.py`, zmienione pliki w `archive/`, `index.html`.

## Zasady
- Jedno zadanie = jeden PR do `main`. Opis PR po polsku: co zmienione, jak sprawdzone.
- Zmieniaj tylko pliki wymienione w zadaniu oraz pliki tworzone przez `generator.py`.
- Bez wyraźnego polecenia w zadaniu: nie usuwaj plików, nie rób revertów, nie przepisuj całych plików, nie zmieniaj wyglądu strony.
- Nie wymyślaj danych: tytułów, ID Suno, tekstów, linków. Dane podaje właściciel w treści zadania.
- Brak danych albo niejasne zadanie: zatrzymaj się i zadaj pytanie w PR.
- Nie commituj `__pycache__/`, `*.pyc`, `site/`.
