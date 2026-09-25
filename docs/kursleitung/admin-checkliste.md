# Admin-Checkliste (Kursleitung)

## Claude Enterprise
- [ ] Die 30 Studierenden aufnehmen, idealerweise über SSO bzw. SCIM mit ihren HSG-Accounts. Dafür eine eigene Gruppe "CAS Agentic AI" anlegen.
- [ ] Seats **mit Claude-Code-Zugang** zuweisen. Vorher prüfen, ob der Seat-Typ Claude Code enthält.
- [ ] Claude Code im Web für die Org aktivieren.
- [ ] Nutzungs- bzw. Ausgabenlimits für die Kursgruppe setzen.
- [ ] **Gmail-Connector** freigeben.
- [ ] **Websuche** prüfen und aktivieren (nötig für Task 0).
- [ ] Optional: über Managed Settings zentral festlegen, welche Befehle erlaubt sind.

## GitHub
Jede Person braucht einen **eigenen** GitHub-Account. Ein geteilter Account kommt nicht in Frage: Er verstösst gegen die GitHub-Nutzungsbedingungen, macht die privaten Daten aller für alle sichtbar und scheitert an 2FA.

- [ ] Eine Kurs-Organisation auf GitHub anlegen, z.B. `hsg-agentic-ai-2026`.
- [ ] Die **Claude GitHub App** für die ganze Organisation installieren: https://github.com/apps/claude/installations/select_target. Fehlt sie, bekommen die Studierenden beim Push den Fehler **403**.
- [ ] `template/` als eigenes Template-Repo in die Organisation legen.
- [ ] Ein GitHub-Classroom-Assignment aus dem Template erstellen. Die Studierenden klicken dann einen Link, und es entsteht automatisch ein **privates** Repo pro Person.

## Cloud-Umgebung (Claude Code im Web)
- [ ] Unter **Network access** `youtube.com` und `www.youtube.com` erlauben. Einstellung: Cloud-Environment-Menü in der Titelleiste der Session → Edit. Doku: https://code.claude.com/docs/en/claude-code-on-the-web
- [ ] **Setup-Script** festlegen: pandas, requests, gegebenenfalls youtube-transcript-api.
- [ ] Klären, ob sich eine Umgebung zentral für alle vorgeben lässt. Wenn nicht, braucht die Setup-Anleitung einen zusätzlichen Schritt (siehe [`offene-punkte.md`](offene-punkte.md)).

## Kommunikation mit den Studierenden
- [ ] Ca. 1 Woche vorher die [Setup-Hausaufgabe](../studierende/setup-hausaufgabe.md) verschicken.
- [ ] Ein Formular einrichten, das GitHub-Username, `…XAgt`-Adresse und "Test hat funktioniert" abfragt.
- [ ] Optional: am Vortag eine 30-minütige Online-Setup-Sprechstunde anbieten.

## Probelauf
- [ ] 2–3 **Test-Accounts** anlegen, die wie Studierende eingerichtet sind: neuer GitHub-Account, normaler Seat, kein Admin.
- [ ] Alle drei Blöcke vollständig durchspielen, inklusive Gmail-Connector und Websuche.
