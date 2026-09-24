# Handoff: Agentic-AI-Kurs mit Claude Code (CAS Exec, HSG)

> Zweck dieses Dokuments: Ein anderes LLM bzw. eine neue Session soll ohne Vorwissen nahtlos weiterarbeiten können.
> Stand: 2026-09-24. Sprache mit der Kursleitung: **Deutsch**.

---

## 1. Ausgangslage

- **Kursleitung:** Dozent·in an der Universität St. Gallen (HSG).
- **Zielgruppe:** ca. **30 CAS-Exec-Studierende**, sehr divers. Sie haben Vorwissen in Machine Learning und Data Analytics, aber **nicht unbedingt in Softwareentwicklung**. Viele nutzen Firmen-Laptops.
- **Format:** **3 Blöcke à 75 Minuten.**
- **Ziel:** Theorie zu Agentic AI, idealerweise inklusive Multi-Agent-Systemen, dazu Hands-on mit **Claude Code**.
- **Vorhanden:**
  - Die Kursleitung hat **bereits Folien** für die Theorie. Sie sind noch nicht hochgeladen; ideal wäre, die Übungen darauf abzustimmen.
  - Es gibt eine **Claude-Enterprise-Umgebung**.
  - Es existiert ausserdem ein weiterer Exec-Kurs. Unklar ist, ob daraus Material wiederverwendet werden soll → nachfragen.
- **Repo:** `hagamble/TeachingAgenticAI`, Arbeitsbranch `claude/wonderful-hawking-hrk5r8`. Das Repo ist bisher ein leeres Lab-Template (README mit Platzhaltern, leere Ordner `docs/ notes/ experiments/ src/ data/ results/`).

## 2. Getroffene Entscheidungen

| Thema | Entscheidung |
|---|---|
| Oberfläche | **Claude Code im Web** (claude.ai/code), keine lokale Installation (Firmen-Laptops ohne Admin-Rechte, Proxies) |
| Accounts | Enterprise-Seats mit Claude-Code-Zugang; Login mit HSG-Account (SSO/SCIM, falls möglich); eigene Gruppe für den Kurs |
| GitHub | **Jede Person braucht einen eigenen GitHub-Account.** Ein geteilter Account verstösst gegen die GitHub-Nutzungsbedingungen, macht alle privaten Daten für alle sichtbar und scheitert an 2FA. Lösung: eine **Kurs-Organisation auf GitHub** mit **Claude GitHub App** (einmal für die Organisation installiert) und **GitHub Classroom**. Die Studierenden klicken einen Assignment-Link, und es entsteht automatisch ein privates Repo pro Person aus dem Template |
| Second Brain | **Markdown im Repo nach Karpathy** (LLM-Wiki): `raw/` enthält Rohquellen, `wiki/` enthält die vom LLM gepflegten, verlinkten Seiten plus `index.md`. Kostenlos, ohne zusätzlichen Account. **Obsidian** ist nur optional als Anzeige zu Hause, weil es denselben Ordner öffnen kann. Notion wurde verworfen (zusätzlicher Account, OAuth, fehleranfällige API-Schreibzugriffe) |
| Durchgehender Case | "**Mein persönlicher Agent**": Jede Person baut über alle drei Blöcke ihr eigenes System auf |
| Capture-Kanal | Pro Person ein eigener **Gmail-Account `NameXAgt`** (bei vergebenem Namen z.B. `vorname.nachnamexagt`). Inhalte werden am Handy per "Teilen" an diese Adresse geschickt. Der Agent liest sie über den **Gmail-Connector** |
| Datenschutz | Repos **müssen privat** sein. Die Selbstrecherche ist freiwillig; als Alternative können CV- oder LinkedIn-Text eingefügt werden. Keine Firmendaten verwenden |

## 3. Kursaufbau (3 × 75 Min.)

Schema pro Block: **ca. 20 Min. Theorie (Folien der Kursleitung), 40 Min. Hands-on, 15 Min. Debrief.**

### Block 1: Digital Self und Second Brain anlegen
- Theorie: vom LLM zum Tool Use zum Agent Loop (Wahrnehmen, Planen, Handeln, Beobachten). Wann Workflow, wann Agent (Anthropic, "Building Effective Agents").
- Setup-Check (maximal 10 Min.). Wer nicht läuft, arbeitet ab jetzt in einem Paar mit.
- **Task 0:** "Recherchiere alles, was online über mich zu finden ist", mit Quellenangaben (Websuche).
  - Lehrmoment: Bei häufigen Namen findet der Agent falsche Personen oder halluziniert. Daran lassen sich Verifikation und Human-in-the-Loop zeigen. Die Studierenden korrigieren selbst.
- Das Ergebnis wird der Startinhalt des Second Brain: `wiki/ich.md`, `wiki/themen/…`, `wiki/index.md`.

### Block 2: Inbox und Capture-Problem
- Use Case: Beim Scrollen sieht man etwas Hilfreiches, und es geht unter.
- Ablauf: am Handy "Teilen", an `…XAgt@gmail.com` schicken. Der Agent liest die Inbox, holt zu jedem Link Metadaten, fasst zusammen, verschlagwortet und sortiert den Inhalt ins Wiki ein, mit Verlinkung zu bestehenden Seiten.
- Theorie: Kontext, Memory, Tools und MCP bzw. Connectors, Permissions, Autonomiestufen.
- Verpackt als **Skill `/inbox`**. Optional als tägliche **Routine** (automatisch jeden Morgen), um den Unterschied zwischen Chat und Agent zu zeigen.

### Block 3: Multi-Agent zwischen zwei Personen
- Jede Person erzeugt aus ihrem Second Brain eine **öffentliche Profilkarte** (Skill `/profilkarte`). Das Wiki selbst wird nicht geteilt.
- Zu zweit werden die Karten ausgetauscht. Drei Subagents spielen das Szenario: `agent-a` vertritt Person A, `agent-b` vertritt Person B, `moderator` leitet das Gespräch. Pattern: Orchestrator-Worker.
- Ergebnis: ein konkreter Vorschlag, z.B. ein gemeinsames Projekt, eine Geschäftsidee oder gegenseitige Hilfe.
- Debrief für Execs: Was darf mein Agent preisgeben? Wer haftet, wenn Agenten verhandeln? Governance, Kosten, Evaluation.

## 4. Geplante Repo-Struktur (Template für GitHub Classroom), noch nicht gebaut

```
README.md                    # Kurzanleitung für Studierende
CLAUDE.md                    # Regeln fürs Wiki (Karpathy-Stil), Ton: jeden Schritt erklären, Quellen nennen
.claude/settings.json        # vorab erlaubte Befehle (python, pip, curl …) → weniger Permission-Prompts
.claude/skills/
  recherche-ich/SKILL.md     # Task 0: Websuche zur eigenen Person → raw/ + wiki/
  inbox/SKILL.md             # Gmail lesen → Links anreichern → wiki einsortieren
  profilkarte/SKILL.md       # öffentliche Profilkarte aus dem Wiki erzeugen
.claude/agents/
  agent-a.md                 # vertritt Person A (liest profilkarte-a.md)
  agent-b.md                 # vertritt Person B (liest profilkarte-b.md)
  moderator.md               # führt den Dialog, schreibt das Ergebnis
raw/                         # Rohquellen (Rechercheergebnisse, Mails)
wiki/index.md                # Einstieg ins Second Brain
exercises/block1.md …block3.md   # Übungsblätter mit getesteten Prompts + Fallbacks
docs/setup-studierende.md    # Hausaufgabe/Setup-Check (Schritt für Schritt, für Nicht-Entwickler)
docs/admin-checkliste.md     # für die Kursleitung
```
Zusätzlich: **Checkpoints pro Block** (z.B. Branches oder Tags `block2-start`, `block3-start`), damit Nachzügler oder Abwesende einsteigen können. Web-Sessions sind nicht dauerhaft, deshalb muss die Arbeit jeweils gepusht werden.

## 5. Vorab-To-dos

### Kursleitung (Admin)
- [ ] 30 Studierende in die Enterprise-Umgebung aufnehmen und Seats **mit Claude-Code-Zugang** zuweisen (prüfen, ob der Seat-Typ Claude Code enthält)
- [ ] Claude Code im Web für die Org aktivieren; Nutzungs- bzw. Ausgabenlimits für die Kursgruppe setzen
- [ ] **Gmail-Connector** in der Enterprise-Umgebung freigeben
- [ ] **Websuche** für die Org prüfen und aktivieren (nötig für Task 0)
- [ ] GitHub-Organisation anlegen, Claude GitHub App installieren, GitHub Classroom und das Assignment aus dem Template einrichten
- [ ] **Netzwerk-Policy** der Cloud-Umgebung: `youtube.com` und `www.youtube.com` erlauben (siehe Abschnitt 6). Einstellung: Cloud-Environment-Menü in der Titelleiste der Session → Edit → Network access. Doku: https://code.claude.com/docs/en/claude-code-on-the-web
- [ ] Setup-Script der Umgebung festlegen (pandas, requests, ggf. youtube-transcript-api)
- [ ] Offen: Kann eine Umgebung zentral für alle Org-Mitglieder vorgegeben werden? Sonst muss jede Person Netzwerk und Setup selbst einstellen (Anleitung nötig). Beim Anthropic-Ansprechpartner nachfragen
- [ ] **Probelauf** mit 2–3 Test-Accounts wie Studierende: neuer GitHub-Account, normaler Seat, kein Admin. Alle drei Blöcke durchspielen

### Studierende (Hausaufgabe, ca. 1 Woche vorher)
- [ ] Gmail-Account `NameXAgt` anlegen (**nicht erst im Kurs**: Google verlangt eine Telefonverifikation und sperrt bei vielen Anmeldungen aus demselben Netz)
- [ ] Einen GitHub-Account anlegen, falls noch keiner vorhanden ist
- [ ] Mit dem HSG-Account bei Claude einloggen und GitHub verbinden
- [ ] Den Gmail-Connector mit dem `…XAgt`-Account verbinden (**nicht** mit der privaten oder der Firmen-Mail)
- [ ] Den Classroom-Link anklicken und einen Test-Prompt im eigenen Repo ausführen
- [ ] Zum Testen eine Mail vom Handy an `…XAgt` schicken
- [ ] Formular ausfüllen: GitHub-Username, `…XAgt`-Adresse, "Test hat funktioniert"

## 6. Technische Befunde und Risiken

1. **YouTube wurde getestet (2026-09-24) und ist aktuell BLOCKIERT.** In der Cloud-Umgebung dieser Session lieferten `https://www.youtube.com/oembed?...` und `youtube-transcript-api` beide `403 CONNECT tunnel failed`, d.h. die Netzwerk-Policy verweigert die Verbindung. Das betrifft die Studierenden genauso.
   - Nach der Freigabe erneut testen: (a) oEmbed für Titel und Kanal, (b) die Videoseite für die Beschreibung, (c) Transkripte. YouTube blockiert Transkript-Abrufe von Cloud-IPs erfahrungsgemäss oft.
   - **Designvorgabe für `/inbox`:** Der Skill muss **ohne Transkript** funktionieren (Titel, Kanal, Beschreibung plus der Text, den die Person in die Mail geschrieben hat). Das Transkript ist ein Bonus. Artikel-Links funktionieren meist problemlos.
2. **Gmail-Connector:** muss vom Enterprise-Admin freigegeben werden. Die Kombination "HSG-Claude-Account plus separater Gmail-Account im Connector" im Probelauf testen. Fallback ist IMAP mit App-Passwort (braucht 2FA, Secrets in der Umgebung und die Netzwerkfreigabe für `imap.gmail.com`), bedeutet aber viel mehr Reibung.
3. **Websuche:** Verfügbarkeit in der Enterprise-Umgebung prüfen, denn Task 0 hängt davon ab.
4. **Nicht-Entwickler:** Aufgaben klein und lösbar halten, alle Prompts vorher durchspielen, Paararbeit ermöglichen, eine Hilfsperson pro 10–15 Studierende einplanen, eine Fallback-Live-Demo am Bildschirm der Kursleitung vorbereiten.

## 7. Offene Fragen an die Kursleitung

1. Folien hochladen (PPTX oder PDF), damit die Übungen darauf abgestimmt werden können?
2. "Ich hab auch einen Exec-Kurs": Soll Material daraus wiederverwendet werden, oder ist es ein zweiter Kurs, der ebenfalls Material braucht?
3. Finden die 3 Blöcke am selben Tag statt oder verteilt? Das ist wichtig für Checkpoints und das Pushen.
4. Wurde `youtube.com` in der Netzwerk-Policy freigegeben? Dann zuerst den Test aus 6.1 wiederholen.
5. Szenario für Block 3 festlegen: gemeinsames Projekt, Geschäftsidee, Mentoring, Verhandlung?

## 8. Nächste Schritte für das übernehmende LLM

1. Die offenen Fragen aus Abschnitt 7 klären (Deutsch, kurz).
2. Falls YouTube freigegeben ist: den Test aus 6.1 ausführen und das Ergebnis dokumentieren.
3. Das Template-Repo gemäss Abschnitt 4 bauen: `CLAUDE.md`, `.claude/settings.json`, die Skills `recherche-ich`, `inbox`, `profilkarte`, die Subagents `agent-a`, `agent-b`, `moderator`, Übungsblätter mit Fallbacks, Setup-Anleitung für Studierende, Admin-Checkliste.
4. Alles auf Branch `claude/wonderful-hawking-hrk5r8` committen und pushen. Keinen PR erstellen, ausser die Kursleitung verlangt es.
