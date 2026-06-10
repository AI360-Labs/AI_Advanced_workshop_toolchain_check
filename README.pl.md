# Gen AI Advanced — Weryfikacja środowiska przed warsztatem

Witaj! Przed warsztatem zapoznaj się z tym przewodnikiem i sprawdź, czy Twoje środowisko i dostępy do usług są gotowe na szkolenie.

---

## Zalecana konfiguracja

- **GitHub Codespaces (darmowy plan)** — najłatwiejszy sposób na gotowe środowisko bez lokalnej instalacji.
- **Środowisko lokalne** — również obsługiwane, jeśli wolisz pracować na własnej maszynie.

> **Uwaga:** Odradzamy korzystanie z laptopów służbowych. Polityki bezpieczeństwa firm często blokują dostęp do zewnętrznych usług wykorzystywanych podczas warsztatu.

---

## Krok 1 — Utwórz własne repozytorium

Podczas warsztatu będziesz budować własny projekt, dlatego utwórz **nowe, puste repozytorium** na GitHubie, w którym będziesz przechowywać swoją pracę:

1. Przejdź do [github.com/new](https://github.com/new).
2. Nadaj mu nazwę (np. `gen-ai-advanced`), ustaw jako **Private** lub **Public** — według uznania.
3. Kliknij **Create repository**.

Będziesz tutaj wrzucać kod podczas warsztatu, żeby zabrać go ze sobą po sesji.

---

## Krok 2 — Otwórz w GitHub Codespaces

1. Na stronie swojego repozytorium kliknij zielony przycisk **Code**.
2. Wybierz zakładkę **Codespaces**.
3. Kliknij **Create codespace on main**.

Darmowy plan obejmuje 60 godzin/miesiąc korzystania z Codespaces — w zupełności wystarczy na warsztat.

---

## Krok 3 — Środowisko Python

Warsztat używa **Pythona 3.13** i **[uv](https://docs.astral.sh/uv/)** jako menedżera pakietów.

Jeśli pracujesz **lokalnie**, zainstaluj oba przed sesją:

- **Python 3.13** — [python.org/downloads](https://www.python.org/downloads/)
- **uv** — [docs.astral.sh/uv/getting-started/installation](https://docs.astral.sh/uv/getting-started/installation/)

  Szybka instalacja (macOS/Linux):
  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```
  Na Windows (PowerShell):
  ```powershell
  powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
  ```

Sprawdź dostępność obu narzędzi:
```bash
python3 --version   # powinno wyświetlić Python 3.13.x
uv --version
```

Jeśli korzystasz z **GitHub Codespaces**, oba są już zainstalowane i nie wymaga dodatkowej konfiguracji.

---

## Krok 4 — IDE

Podczas warsztatu będziemy używać **Visual Studio Code**. Na Codespaces VS Code otwiera się automatycznie w przeglądarce (lub możesz połączyć się przez aplikację desktopową).

Jeśli pracujesz lokalnie, pobierz VS Code ze strony [code.visualstudio.com](https://code.visualstudio.com), jeśli jeszcze go nie masz.

> Możesz korzystać z innego IDE, jeśli zdecydowanie je preferujesz, jednak nie będziemy w stanie zapewnić wsparcia dla niego podczas sesji.

---

### OpenRouter (dostęp do API modeli LLM)

OpenRouter zapewnia dostęp do wielu modeli AI przez jedno API. Klucze API będziemy przydzielać podczas warsztatu.

**Bez konta (tylko weryfikacja połączenia):**

```bash
curl -o /dev/null -s -w "%{http_code}" https://openrouter.ai/api/v1/models
```

Odpowiedź `200` potwierdza, że Twoja sieć może połączyć z OpenRouter. Kod `401` lub `403` również oznacza, że połączenie działa — potrzebujesz tylko klucza. Każdy inny błąd (timeout, `000`) sugeruje blokadę sieciową.

---

### Supabase (dostęp do bazy danych)

Supabase oferuje hostowaną bazę danych Postgres z API REST. Będziemy jej używać do przechowywania danych agenta.

**Bez konta (tylko weryfikacja połączenia):**

```bash
curl -o /dev/null -s -w "%{http_code}" https://supabase.com
```

Kod `200` potwierdza, że Twoja sieć może połączyć się z Supabase.

---

## Lista kontrolna

Przed sesją potwierdź, że:

- [ ] Masz dostęp do repozytorium GitHub warsztatu
- [ ] Masz utworzone własne repozytorium na GitHubie
- [ ] Możesz otworzyć Codespace (lub masz działające lokalne środowisko)
- [ ] Python 3.13 i uv są dostępne w Twoim środowisku
- [ ] VS Code jest dostępny (Codespaces lub lokalna instalacja)
- [ ] Możesz połączyć się z `openrouter.ai` — najlepiej z działającym kluczem API
- [ ] Możesz połączyć się z `supabase.com` — najlepiej z utworzonym projektem i gotowym kluczem API

Jeśli cokolwiek jest zablokowane, skontaktuj się z nami: kontakt@ai360labs.pl

---

## Pytania?

Skontaktuj się z organizatorami warsztatu lub otwórz issue w tym repozytorium.
