# Handoff: Agentic-AI-Kurs mit Claude Code (CAS Exec, HSG)

> **Zweck:** Eine neue Session bzw. ein anderes LLM soll ohne Vorwissen weiterarbeiten können.
> **Stand:** 2026-09-25 · **Sprache mit der Kursleitung:** Deutsch
> **Repo:** `hagamble/TeachingAgenticAI` · **Arbeitsbranch:** `claude/wonderful-hawking-hrk5r8` (noch nicht nach `main` gemergt)

## Zuerst lesen
| Datei | Inhalt |
|---|---|
| [`kursleitung/kursplan.md`](kursleitung/kursplan.md) | Ablauf der 3 Blöcke mit Theorie, Hands-on und Debrief |
| [`kursleitung/kommunikationsplan.md`](kursleitung/kommunikationsplan.md) | Welche Information wann und über welchen Kanal an die Teilnehmenden geht |
| [`kursleitung/admin-checkliste.md`](kursleitung/admin-checkliste.md) | Vorab-To-dos der Kursleitung: Enterprise, GitHub, Netzwerk, Probelauf |
| [`kursleitung/offene-punkte.md`](kursleitung/offene-punkte.md) | Offene Fragen, Risiken und Befunde (u.a. der YouTube-Test) |
| [`studierende/setup-hausaufgabe.md`](studierende/setup-hausaufgabe.md) | Setup-Anleitung für Studierende; Platzhalter `[…]` sind noch auszufüllen |
| [`../template/README.md`](../template/README.md) | Geplante Struktur des Starter-Repos für Studierende |

## Ausgangslage
- **Zielgruppe:** ca. **30 CAS-Exec-Studierende** mit Vorwissen in ML und Data Analytics, aber **nicht unbedingt in Softwareentwicklung**. Viele nutzen Firmen-Laptops.
- **Format:** **3 × 75 Minuten.** Inhalt: Theorie zu Agentic AI und Multi-Agent-Systemen, dazu Hands-on mit **Claude Code**.
- **Vorhanden:**
  - Es gibt eine **Claude-Enterprise-Umgebung**.
  - Die **Folien** der Kursleitung existieren, sind aber noch nicht hochgeladen. Sie gehören nach `slides/`.

## Getroffene Entscheidungen (nicht neu diskutieren)
| Thema | Entscheidung |
|---|---|
| Oberfläche | **Claude Code im Web**, keine lokale Installation |
| Accounts | Enterprise-Seats mit Claude-Code-Zugang, Login mit dem HSG-Account |
| GitHub | **Eigener Account pro Person.** Dazu eine Kurs-Organisation mit der Claude GitHub App und **GitHub Classroom**, das pro Person ein privates Repo aus `template/` erzeugt |
| Second Brain | **Markdown im Repo nach Karpathy:** `raw/` und `wiki/`. Obsidian ist nur optional als Anzeige; Notion wurde verworfen |
| Durchgehender Case | "Mein persönlicher Agent": Digital Self, Second Brain, Inbox-Agent, Multi-Agent zwischen zwei Personen |
| Capture | Pro Person ein Gmail-Account **`NameXAgt`**, gelesen über den **Gmail-Connector** |
| Datenschutz | Private Repos, Selbstrecherche freiwillig (Alternative: CV-Text), keine Firmendaten |

## Nächste Schritte
1. Die offenen Fragen in `kursleitung/offene-punkte.md` mit der Kursleitung klären.
2. Falls YouTube freigegeben ist, den Test aus `offene-punkte.md` wiederholen und das Ergebnis dort dokumentieren.
3. Das **Starter-Repo in `template/`** gemäss `template/README.md` bauen: `CLAUDE.md`, `.claude/settings.json`, die Skills, die Subagents, `raw/`, `wiki/`, die Übungsblätter mit Fallbacks.
4. Sobald Folien in `slides/` liegen, die Übungen darauf abstimmen.
5. Auf dem Arbeitsbranch committen und pushen. Einen PR nur erstellen, wenn die Kursleitung es verlangt.
