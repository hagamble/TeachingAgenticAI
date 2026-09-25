# Offene Punkte, Risiken und Befunde

## Offene Fragen an die Kursleitung
1. **Folien:** Bitte in [`slides/`](../../slides/) ablegen (PPTX oder PDF), damit die Übungen darauf abgestimmt werden können.
2. **Anderer Exec-Kurs:** Soll Material daraus wiederverwendet werden, oder ist es ein zweiter Kurs, der eigenes Material braucht?
3. **Termine:** Finden die 3 Blöcke am selben Tag statt oder verteilt? Davon hängen die Checkpoints und das Pushen ab.
4. **Block 3:** Welches Szenario? Gemeinsames Projekt, Geschäftsidee, Mentoring oder Verhandlung?
5. **YouTube:** Ist `youtube.com` in der Netzwerk-Policy freigegeben? Danach den Test unten wiederholen.

## Technische Befunde

### YouTube ist blockiert (getestet am 2026-09-24)
In der Cloud-Umgebung lieferten `https://www.youtube.com/oembed?...` und `youtube-transcript-api` beide `403 CONNECT tunnel failed`. Die Netzwerk-Policy verweigert also die Verbindung. Das betrifft die Studierenden genauso.

**Nach der Freigabe erneut testen:**
- (a) oEmbed für Titel und Kanal
- (b) die Videoseite für die Beschreibung
- (c) Transkripte. YouTube blockiert Transkript-Abrufe von Cloud-IPs erfahrungsgemäss oft.

**Designvorgabe für `/inbox`:** Der Skill muss ohne Transkript funktionieren. Er nutzt Titel, Kanal, Beschreibung und den Text, den die Person selbst in die Mail geschrieben hat. Das Transkript ist ein Bonus. Artikel-Links funktionieren meist problemlos.

### GitHub-Push 403 (2026-09-24, inzwischen behoben)
Die Claude GitHub App hatte keinen Zugriff auf das Repo. Nach der Installation bzw. dem Neuverbinden ging es. Dasselbe Problem droht den Studierenden, wenn die App nicht für die Kurs-Organisation installiert ist.

## Risiken
| Risiko | Gegenmassnahme |
|---|---|
| Gmail-Accounts erst im Kurs anlegen (Telefonverifikation, Google sperrt bei vielen Anmeldungen aus demselben Netz) | Als Hausaufgabe vorab erledigen lassen |
| Gmail-Connector funktioniert nicht mit einem separaten Gmail-Account neben dem HSG-Claude-Account | Im Probelauf testen. Fallback ist IMAP mit App-Passwort, das braucht 2FA, Secrets und die Netzwerkfreigabe für `imap.gmail.com` |
| Websuche in der Enterprise-Umgebung nicht aktiv | Vorher prüfen; Fallback ist der Text aus CV oder LinkedIn |
| Umgebung lässt sich nicht zentral vorgeben | Anleitung für Netzwerk und Setup-Script in die Hausaufgabe aufnehmen |
| Datenschutz bei der Selbstrecherche | Private Repos, Teilnahme freiwillig, keine Firmendaten |
