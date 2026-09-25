# Kursplan: 3 × 75 Minuten

**Durchgehender Case: "Mein persönlicher Agent".** Jede Person baut über alle drei Blöcke ihr eigenes System auf. Jeder Block baut auf dem vorherigen auf.

**Schema pro Block:** ca. 20 Min. Theorie (Folien in [`slides/`](../../slides/)), 40 Min. Hands-on, 15 Min. Debrief.

---

## Block 1: Digital Self und Second Brain anlegen

**Theorie:** vom LLM zum Tool Use zum Agent Loop (Wahrnehmen, Planen, Handeln, Beobachten). Wann ein Workflow reicht und wann es einen Agenten braucht (Anthropic, "Building Effective Agents").

**Hands-on:**
1. Setup-Check, maximal 10 Min. Wer nicht läuft, arbeitet ab jetzt im Paar mit.
2. **Task 0:** "Recherchiere alles, was online über mich zu finden ist", mit Quellenangaben (Websuche).
3. Das Ergebnis wird der Startinhalt des Second Brain nach Karpathy:
   - `raw/` enthält die Rohquellen.
   - `wiki/` enthält die vom LLM gepflegten, verlinkten Seiten: `wiki/ich.md`, `wiki/themen/…` und `wiki/index.md`.

**Lehrmoment:** Bei häufigen Namen findet der Agent falsche Personen oder halluziniert. Daran lassen sich Verifikation und Human-in-the-Loop zeigen: Die Studierenden korrigieren das Ergebnis selbst.

**Alternative zu Task 0:** Wer sich nicht selbst recherchieren lassen will, fügt stattdessen den Text aus CV oder LinkedIn-Profil ein.

---

## Block 2: Inbox und das Capture-Problem

**Use Case:** Beim Scrollen sieht man etwas Hilfreiches, und es geht unter.

**Theorie:** Kontext, Memory, Tools und MCP bzw. Connectors, Permissions, Autonomiestufen.

**Hands-on:**
1. Am Handy einen YouTube- oder Artikel-Link über "Teilen" an `…XAgt@gmail.com` schicken.
2. Der Agent liest die Inbox über den Gmail-Connector.
3. Zu jedem Link holt er Metadaten, fasst zusammen, verschlagwortet und sortiert den Inhalt ins Wiki ein, mit Verlinkung zu bestehenden Seiten.
4. Das Ganze wird als **Skill `/inbox`** verpackt und ist damit mit einem Befehl wiederholbar.
5. Optional: als tägliche **Routine**, die automatisch jeden Morgen läuft. Das zeigt den Unterschied zwischen Chat und Agent.

**Wichtig:** `/inbox` muss **ohne YouTube-Transkript** funktionieren. Details dazu in [`offene-punkte.md`](offene-punkte.md).

---

## Block 3: Multi-Agent zwischen zwei Personen

**Theorie:** Orchestrator-Worker, Evaluator-Optimizer, Parallelisierung, Kosten und Risiken.

**Hands-on:**
1. Jede Person erzeugt mit dem Skill `/profilkarte` eine **öffentliche Profilkarte** aus ihrem Second Brain. Das Wiki selbst wird nicht geteilt.
2. Zu zweit tauschen die Studierenden ihre Karten aus.
3. Drei Subagents spielen das Szenario durch:
   - `agent-a` vertritt Person A.
   - `agent-b` vertritt Person B.
   - `moderator` leitet das Gespräch und schreibt das Ergebnis.
4. Das Ergebnis ist ein konkreter Vorschlag, zum Beispiel ein gemeinsames Projekt, eine Geschäftsidee oder gegenseitige Hilfe. Welches Szenario es wird, ist noch offen.

**Debrief für Execs:** Was darf mein Agent preisgeben? Wer haftet, wenn Agenten verhandeln? Dazu Governance, Kosten und Evaluation.

---

## Didaktische Grundregeln
- Aufgaben klein und lösbar halten, alle Prompts vorher durchspielen.
- Den Agent Loop sichtbar machen: Die Studierenden sollen beobachten, was der Agent tut, nicht nur das Ergebnis sehen.
- **Checkpoints pro Block** (`block2-start`, `block3-start`), damit Nachzügler oder Abwesende einsteigen können.
- Web-Sessions sind nicht dauerhaft, deshalb die Arbeit am Blockende pushen.
- Paararbeit ermöglichen; eine Hilfsperson pro 10–15 Studierende einplanen.
- Eine Fallback-Live-Demo am Bildschirm der Kursleitung bereithalten.
