# MCP Atlassian - Untersuchungsergebnisse

## Zusammenfassung

Dieses Dokument enthält die Ergebnisse der Untersuchung der verfügbaren MCP (Model Context Protocol) Schnittstellen im Kontext dieses Repositories.

## Zielsetzung

Die Aufgabe war es, testweise Atlassian MCP Ressourcen über die verfügbare MCP Schnittstelle auszulesen und die Ergebnisse als Markdown zurückzuliefern.

## Ergebnisse der Untersuchung

### Verfügbare MCP Tools

Nach der Analyse der verfügbaren Tools wurde festgestellt, dass **keine Atlassian MCP Tools** im aktuellen Kontext verfügbar sind. Stattdessen stehen folgende MCP-Schnittstellen zur Verfügung:

#### 1. GitHub MCP Server Tools

Die folgenden GitHub-bezogenen MCP Tools sind verfügbar:

##### Repository-Verwaltung
- `search_repositories` - Repository-Suche auf GitHub
- `search_code` - Code-Suche über alle GitHub Repositories
- `search_issues` - Issues durchsuchen
- `search_pull_requests` - Pull Requests durchsuchen
- `search_users` - GitHub Benutzer suchen

##### Code & Datei-Operationen
- `get_file_contents` - Dateiinhalte aus einem Repository abrufen
- `list_branches` - Branches auflisten
- `list_commits` - Commits auflisten
- `get_commit` - Details zu einem Commit abrufen
- `list_tags` - Git Tags auflisten
- `get_tag` - Details zu einem Tag abrufen

##### Issues & Pull Requests
- `list_issues` - Issues in einem Repository auflisten
- `get_issue` - Details zu einem Issue abrufen
- `get_issue_comments` - Kommentare zu einem Issue abrufen
- `list_sub_issues` - Sub-Issues auflisten
- `list_issue_types` - Unterstützte Issue-Typen auflisten
- `list_pull_requests` - Pull Requests auflisten
- `get_pull_request` - Details zu einem Pull Request abrufen
- `get_pull_request_diff` - Diff eines Pull Requests abrufen
- `get_pull_request_files` - Geänderte Dateien in einem PR abrufen
- `get_pull_request_reviews` - Reviews eines PRs abrufen
- `get_pull_request_review_comments` - Review-Kommentare abrufen
- `get_pull_request_status` - Status eines PRs abrufen

##### Workflow & CI/CD
- `list_workflows` - Workflows auflisten
- `list_workflow_runs` - Workflow-Ausführungen auflisten
- `get_workflow_run` - Details zu einer Workflow-Ausführung
- `list_workflow_jobs` - Jobs einer Workflow-Ausführung auflisten
- `get_job_logs` - Logs für Workflow-Jobs abrufen
- `get_workflow_run_logs` - Logs für Workflow-Ausführungen abrufen
- `get_workflow_run_usage` - Nutzungsmetriken für Workflows
- `list_workflow_run_artifacts` - Artifacts auflisten
- `download_workflow_run_artifact` - Artifacts herunterladen
- `summarize_job_log_failures` - Fehlgeschlagene Job-Logs zusammenfassen
- `summarize_run_log_failures` - Fehlgeschlagene Workflow-Runs analysieren

##### Sicherheit
- `list_code_scanning_alerts` - Code-Scanning-Alerts auflisten
- `get_code_scanning_alert` - Details zu einem Code-Scanning-Alert
- `list_secret_scanning_alerts` - Secret-Scanning-Alerts auflisten
- `get_secret_scanning_alert` - Details zu einem Secret-Scanning-Alert

##### Releases
- `list_releases` - Releases auflisten
- `get_latest_release` - Neueste Release abrufen
- `get_release_by_tag` - Release anhand eines Tags abrufen

##### Weitere Features
- `list_starred_repositories` - Gestarrete Repositories auflisten

#### 2. Browser Automation Tools (Playwright)

Zusätzlich stehen Browser-Automatisierungs-Tools zur Verfügung:
- Navigation (`browser_navigate`, `browser_navigate_back`)
- Screenshots (`browser_take_screenshot`)
- Snapshots (`browser_snapshot`)
- Interaktion (`browser_click`, `browser_type`, `browser_fill_form`, etc.)
- Konsolen- und Netzwerk-Monitoring

#### 3. Shell & Datei-Operationen

Standard-Tools für:
- Bash-Kommandos (`bash`)
- Datei-Operationen (`view`, `create`, `str_replace`)
- Fortschrittsberichte (`report_progress`)
- Sicherheitsprüfungen (`gh-advisory-database`)

## Fazit

Im aktuellen Kontext sind **keine Atlassian MCP Tools** (z.B. für Jira, Confluence, Bitbucket) verfügbar. Die Hauptfunktionalität konzentriert sich auf GitHub-Integration über umfangreiche GitHub MCP Server Tools.

## Empfehlung

Um Atlassian-Ressourcen über MCP auszulesen, müssten entsprechende Atlassian MCP Server Tools im Kontext konfiguriert und verfügbar gemacht werden. Diese könnten ähnliche Funktionalitäten für Atlassian-Produkte bereitstellen wie die existierenden GitHub MCP Tools für GitHub.

## Beispiel-Nutzung der verfügbaren GitHub MCP Tools

Um die verfügbaren Tools zu demonstrieren, hier ein Beispiel für dieses Repository:

### Repository-Informationen

**Repository:** tt-don-rnd/test

### Verfügbare Dateien
- `README.md` - Haupt-Readme Datei
- `mermaidtest.mmd` - Mermaid Diagramm-Datei mit einem Flowchart

### Inhalt des Mermaid Diagramms

Das Repository enthält ein Mermaid-Flowchart, das verschiedene Integrationsmöglichkeiten darstellt:
- GitHub als Quelle
- RAWContentLink für Zugriff
- Mögliche Ziele: Confluence, Viewport, Scroll Sites

Dies deutet darauf hin, dass möglicherweise geplant war, Atlassian Confluence als Integrationsziel zu verwenden.

---

*Erstellt am: 2024*
*Dokumenttyp: Untersuchungsbericht*
