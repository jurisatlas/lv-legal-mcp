# Latvia Legal Research MCP Server (`lv-legal-mcp`)

**[Latviešu](#lang-lv) | [English Documentation](#english-documentation)**

---

<a id="lang-lv"></a>
## Juridiskais MCP serveris Latvijas tiesību aktiem un judikatūrai (`lv-legal-mcp`) — Latviešu

### Par šo repozitoriju

Šis repozitorijs satur Model Context Protocol (MCP) serveri, kas savieno jūsu AI lietotni (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline vai Antigravity) tieši ar `likumi.lv` un Latvijas Tiesu portālu (`eli.tiesas.lv` — rajona/pilsētas tiesas, 5 apgabaltiesas, Augstākās tiesas Senāts un Satversmes tiesa).

### Ātra instalēšana (AI lietotnes izvēle)

1. **Lejupielāde:** Noklikšķiniet uz **`<> Code` -> `Download ZIP`** un atarhivējiet mapi savā datorā.
2. **Palaišana:** Veiciet dubultklikšķi uz **`Click_Here_To_Install_Windows.bat`** (Windows) vai **`Click_Here_To_Install_Mac.command`** (macOS).
3. **AI klienta izvēle:** Atzīmējiet izmantotās AI programmas (Claude, Cursor, Windsurf, VS Code, Antigravity), noklikšķiniet uz instalēt un restartējiet savu AI lietotni.

**Drošības piezīme:** Instalētājs darbojas tikai lasīšanas režīmā (read-only) un nepiekļūst jūsu personīgajiem failiem datorā.

### Tiesu instances un oficiālie avoti

| Tiesu instance | Aptvertās tiesas |
|:---|:---|
| **1. instance (Rajona tiesas un Administratīvā rajona tiesa)** | 9 Rajona (pilsētas) tiesas (District/City Courts) & Administratīvā rajona tiesa |
| **2. instance (5 Apgabaltiesas)** | 5 Apgabaltiesas (Rīgas, Kurzemes, Latgales, Vidzemes, Zemgales Regional Courts) & Administratīvā apgabaltiesa |
| **3. instance (Augstākā tiesa / Senāts un Satversmes tiesa)** | Augstākā tiesa / Senāts (Supreme Court of Latvia) & Satversmes tiesa (Constitutional Court) |

- **Likumi.lv Official Legislation Portal (Latvijas Vēstnesis):** [https://likumi.lv](https://likumi.lv) (`likumi.lv`, `vestnesis.lv`, `saeima.lv`)
- **Latvijas Tiesu Portāls (eli.tiesas.lv — Anonymized Judgments of District, Regional & Supreme Courts):** [https://eli.tiesas.lv](https://eli.tiesas.lv) (`tiesas.lv`, `eli.tiesas.lv`, `at.gov.lv`, `satv.tiesa.gov.lv`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Latvia (LV)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Latvia**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | 9 Rajona (pilsētas) tiesas (District/City Courts) & Administratīvā rajona tiesa |
| **Tier 2 — Regional / Cantonal / Appellate** | 5 Apgabaltiesas (Rīgas, Kurzemes, Latgales, Vidzemes, Zemgales Regional Courts) & Administratīvā apgabaltiesa |
| **Tier 3 — Supreme & Constitutional** | Augstākā tiesa / Senāts (Supreme Court of Latvia) & Satversmes tiesa (Constitutional Court) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** Likumi.lv Official Legislation Portal (Latvijas Vēstnesis) — [https://likumi.lv](https://likumi.lv)
  - *Indexed Legislation Domains:* `likumi.lv`, `vestnesis.lv`, `saeima.lv`
- **Court Decisions & Jurisprudence Archives:** Latvijas Tiesu Portāls (eli.tiesas.lv — Anonymized Judgments of District, Regional & Supreme Courts) — [https://eli.tiesas.lv](https://eli.tiesas.lv)
  - *Indexed Judicial & Open Case Law Domains:* `tiesas.lv`, `eli.tiesas.lv`, `at.gov.lv`, `satv.tiesa.gov.lv`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Latvia. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Latvia. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Latvia. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "lv-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/lv-legal-mcp/archive/refs/heads/main.zip",
        "lv-legal-mcp"
      ]
    }
  }
}
```
</details>
