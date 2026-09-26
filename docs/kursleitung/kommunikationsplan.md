# Kommunikationsplan: Welche Information wann und wo?

**Grundprinzip: Just in time.** Jede Information kommt genau dann, wenn die Teilnehmenden sie brauchen, und nicht früher. Exec-Studierende lesen wenig im Voraus. Deshalb gilt: vorher nur das, was *vor* dem Kurs erledigt sein muss. Alles andere kommt im Kurs, und zwar dort, wo gerade gearbeitet wird.

**Pro Information gibt es genau eine Quelle:**
| Kanal | Wofür |
|---|---|
| **E-Mail bzw. Lernplattform** | alles *vor* und *nach* dem Kurs |
| **Folien** | Konzepte, Theorie, das "Warum" |
| **Repo** (`README.md`, `exercises/`) | alles, was man im Kurs *tut*: Aufgaben, Prompts zum Kopieren, Fallbacks |
| **Mündlich bzw. Live-Demo** | Motivation, Vorzeigen, Debrief |

---

## Zeitplan

### T–3 Wochen: Ankündigung (E-Mail bzw. Lernplattform)
Kurz halten, maximal eine Bildschirmseite.
- Worum geht es? "Sie bauen in 3 × 75 Min. Ihren eigenen persönlichen KI-Agenten." Dazu ein Satz zu jedem der 3 Tasks.
- **Keine Programmierkenntnisse nötig.**
- Mitbringen: Laptop (möglichst **kein** stark eingeschränkter Firmen-Laptop), Smartphone, Ladegeräte.
- **Datenschutz-Hinweis:** In Block 1 lässt man online über sich selbst recherchieren. Das ist freiwillig, Alternative ist der eigene CV bzw. LinkedIn-Text. Alles liegt in privaten Repos, keine Firmendaten.
- Hinweis: "In einer Woche folgt eine Setup-Anleitung (ca. 30 Min.)."

### T–1 Woche: Setup-Hausaufgabe (E-Mail bzw. Lernplattform)
- Die Anleitung [`../studierende/setup-hausaufgabe.md`](../studierende/setup-hausaufgabe.md) verschicken: Gmail `NameXAgt`, GitHub, Claude-Login, Gmail-Connector, Classroom-Link, Test.
- Rückmeldeformular mit Frist **T–3 Tage**.
- Optional einen Termin für die Setup-Sprechstunde nennen.

### T–3 Tage: Kontrolle (Kursleitung)
- Das Formular auswerten: Wer ist fertig, wer nicht?
- Die Offenen **persönlich** anschreiben. Wer es nicht schafft, wird für den Kurs einer Partnerin oder einem Partner zugeteilt.
- Erinnerung an alle: "Bitte Gmail- und GitHub-Passwort sowie das Handy für 2FA mitbringen."

### Kurstag, Block 1: Digital Self und Second Brain
| Wann | Was | Wo |
|---|---|---|
| Start | Link zu claude.ai/code und zum eigenen Repo, als **QR-Code** | Folie 1 |
| 0–10 Min. | Setup-Check: "Schreiben Sie 'Hallo' in Ihre Session" | Folie + mündlich |
| Theorie | Agent Loop, Workflow vs. Agent | Folien |
| Hands-on | Aufgabe, Prompts zum Kopieren, Fallback (CV-Text statt Websuche) | `exercises/block1.md` im Repo |
| Debrief | "Wo hat Ihr Agent halluziniert?" | mündlich |
| Ende | "Pushen Sie Ihren Stand." Das ist wichtig, weil Sessions nicht dauerhaft sind | Folie |

### Block 2: Inbox-Agent
| Wann | Was | Wo |
|---|---|---|
| Start | "Schicken Sie jetzt 2–3 Links vom Handy an Ihre `…XAgt`-Adresse." Damit ist die Inbox gefüllt, während die Theorie läuft | Folie |
| Theorie | Tools, MCP und Connectors, Memory, Autonomie | Folien |
| Hands-on | den Skill `/inbox` nutzen und anpassen; Hinweis, dass YouTube-Transkripte fehlen können | `exercises/block2.md` |
| Debrief | Chat vs. Agent vs. Routine | mündlich |
| Checkpoint | Wer zurückliegt, startet von `block2-start` | Folie + `exercises/block2.md` |

### Block 3: Multi-Agent zwischen zwei Personen
| Wann | Was | Wo |
|---|---|---|
| Start | **Paare bilden**, möglichst Personen aus unterschiedlichen Branchen | mündlich |
| Theorie | Orchestrator-Worker, Evaluator, Kosten und Risiken | Folien |
| Hands-on | `/profilkarte` erzeugen, Karte mit dem Paar tauschen, Subagents laufen lassen | `exercises/block3.md` |
| Debrief | Governance: Was darf mein Agent preisgeben, wer haftet? | mündlich bzw. Diskussion |
| Checkpoint | `block3-start` | Folie |

**Das Szenario von Block 3 erst im Kurs verraten.** Es trägt die Überraschung, und die Teilnehmenden sollen sich vorher nicht darauf vorbereiten.

### T+1 Tag: Nachbereitung (E-Mail bzw. Lernplattform)
- Folien als PDF und Link zu den eigenen Repos.
- "Wie mache ich weiter?" Obsidian als Anzeige fürs Second Brain, die Routine für `/inbox` weiterlaufen lassen, weiterführende Ressourcen.
- **Offboarding-Info:** Bis wann laufen die Claude-Seats und die Repos in der Kurs-Organisation? Wie exportiert man das eigene Second Brain (ZIP-Download oder Repo auf den eigenen Account übertragen)?
- Kurze Feedback-Umfrage.

---

## Bewusst NICHT vorab verschicken
- Die Theoriefolien (sonst lesen die Teilnehmenden sie nicht oder nur halb).
- Die Übungsblätter und das Szenario von Block 3.
- Details zu Skills und Subagents. Die Teilnehmenden erleben sie im Kurs.

## Offene Entscheidungen für diesen Plan
- [ ] Welcher Kanal: HSG-Lernplattform oder E-Mail?
- [ ] Konkrete Daten für T–3 Wochen, T–1 Woche, T–3 Tage (hängt von den Kursterminen ab)
- [ ] Wie lange bleiben Seats und Repos nach dem Kurs aktiv?
- [ ] Werden die Folien nach dem Kurs geteilt?
