# Starter-Repo für Studierende (noch nicht gebaut)

Dieser Ordner wird später als **eigenes Template-Repo** in die GitHub-Kurs-Organisation kopiert und über GitHub Classroom verteilt.

## Geplante Struktur
```
README.md                    # Kurzanleitung für Studierende
CLAUDE.md                    # Regeln fürs Wiki (Karpathy-Stil); jeden Schritt erklären, Quellen nennen
.claude/settings.json        # vorab erlaubte Befehle (python, pip, curl …) → weniger Permission-Prompts
.claude/skills/
  recherche-ich/SKILL.md     # Block 1: Websuche zur eigenen Person → raw/ + wiki/
  inbox/SKILL.md             # Block 2: Gmail lesen → Links anreichern → ins Wiki einsortieren
  profilkarte/SKILL.md       # Block 3: öffentliche Profilkarte aus dem Wiki erzeugen
.claude/agents/
  agent-a.md                 # vertritt Person A
  agent-b.md                 # vertritt Person B
  moderator.md               # führt den Dialog, schreibt das Ergebnis
raw/                         # Rohquellen (Rechercheergebnisse, Mails)
wiki/index.md                # Einstieg ins Second Brain
exercises/block1.md … block3.md   # Übungsblätter mit getesteten Prompts und Fallbacks
```
Checkpoints pro Block: `block2-start` und `block3-start`.
