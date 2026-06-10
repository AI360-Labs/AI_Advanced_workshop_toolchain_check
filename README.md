# Gen AI Advanced — Pre-Workshop Setup Check

Welcome! Before the workshop session, please follow this guide to verify that your environment and service access are ready to go.

---

## Recommended Setup

- **GitHub Codespaces (free tier)** — the easiest way to get a ready-to-use environment with no local installation required. We strongly recommend this path.
- **Local environment** — also supported if you prefer to work on your own machine.

> **Note:** We discourage using corporate or work-issued laptops. Company security policies often block access to the external services used in this workshop.

---

## Step 1 — Create Your Own Repository

During the workshop you will build your own project, so please create a **new empty repository** on GitHub to store your work:

1. Go to [github.com/new](https://github.com/new).
2. Give it a name (e.g. `gen-ai-advanced`), set it to **Private** or **Public** — your choice.
3. Click **Create repository**.

You will push your workshop code here as you go, so you can take it home after the session.

---

## Step 2 — Open in GitHub Codespaces

1. On your forked repository page, click the green **Code** button.
2. Select the **Codespaces** tab.
3. Click **Create codespace on main**.

The free tier includes 60 hours/month of Codespaces usage — more than enough for the workshop.

---

## Step 3 — Python Environment

The workshop uses **Python 3.13** and **[uv](https://docs.astral.sh/uv/)** as the package manager.

If you are working **locally**, please install both before the session:

- **Python 3.13** — [python.org/downloads](https://www.python.org/downloads/)
- **uv** — [docs.astral.sh/uv/getting-started/installation](https://docs.astral.sh/uv/getting-started/installation/)

  Quick install (macOS/Linux):
  ```bash
  curl -LsSf https://astral.sh/uv/install.sh | sh
  ```
  On Windows (PowerShell):
  ```powershell
  powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
  ```

Verify both are available:
```bash
python3 --version   # should print Python 3.13.x
uv --version
```

If you are using **GitHub Codespaces**, both are preinstalled and no extra setup is needed.

---

## Step 4 — IDE

We will be using **Visual Studio Code** during the workshop. If you are on Codespaces, VS Code opens automatically in the browser (or connects via the desktop app).

If you are working locally, download VS Code at [code.visualstudio.com](https://code.visualstudio.com) if you don't have it already.

> You are welcome to use a different IDE if you strongly prefer one, but we won't be able to provide support for it during the session.

---

### OpenRouter (LLM API access)

OpenRouter provides access to a range of AI models through a single API. We will provision API keys during the workshop.

**Without an account (connectivity check only):**

```bash
curl -o /dev/null -s -w "%{http_code}" https://openrouter.ai/api/v1/models
```

A response of `200` confirms your network can reach OpenRouter. A `401` or `403` also means connectivity is fine — you just need a key. Any other error (timeout, `000`) suggests a network block.

---

### Supabase (database access)

Supabase provides a hosted Postgres database with a REST API. We will use it for our agent data.

**Without an account (connectivity check only):**

```bash
curl -o /dev/null -s -w "%{http_code}" https://supabase.com
```

A `200` confirms your network can reach Supabase. To fully verify API connectivity.

---

## Checklist

Before the session, confirm the following:

- [ ] You can access the workshop GitHub repository
- [ ] You have created your own repository on GitHub
- [ ] You can open a Codespace (or have a working local environment)
- [ ] Python 3.13 and uv are available in your environment
- [ ] VS Code is available (Codespaces or local install)
- [ ] You can reach `openrouter.ai` — ideally with a working API key
- [ ] You can reach `supabase.com` — ideally with a project created and API key ready

If anything is blocked, please contact us: kontakt@ai360labs.pl

---

## Questions?

Reach out to the workshop organizers or open an issue in this repository.
