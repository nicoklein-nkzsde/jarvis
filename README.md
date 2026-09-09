# Jarvis

Sprach-Eingang für Notizen, Aufgaben und Termine. Einsprechen, sortieren lässt Claude.

- **App:** `index.html`, eine Datei, keine Abhängigkeiten. PWA, läuft offline.
- **Skill:** `/jarvis` (liegt in `~/.claude/skills/jarvis/SKILL.md`)
- **Vault:** Aufgaben landen in `20260908 - claudekaizo/Aufgaben.md`, Rohtext in `Inbox.md`

## Einrichten

1. **Repo für die App anlegen** (öffentlich, GitHub Pages):

   ```
   gh repo create jarvis --public --source=. --push
   ```

   Dann in den Repo-Einstellungen Pages auf Branch `main` stellen.
   Adresse aufs iPhone, in Safari öffnen, Teilen → Zum Home-Bildschirm.

2. **Privates Repo für den Eingang** anlegen, z. B. `jarvis-inbox`, mit einem Ordner `inbox/`.

3. **Token erzeugen:** GitHub → Settings → Developer settings → Fine-grained tokens.
   Nur `jarvis-inbox` auswählen, Permission `Contents: Read and write`, Laufzeit 1 Jahr.

4. **In der App** unter ⚙ Konto, Repo, Branch, Ordner und Token eintragen, Verbindung testen.

5. **Auf dem Mac** den Eingang klonen, dahin schaut der Skill:

   ```
   git clone git@github.com:<konto>/jarvis-inbox.git ~/.jarvis-inbox
   ```

## Benutzen

Auf dem iPhone Knopf antippen, reden, nochmal antippen. Text steht sofort da und ist
editierbar. Art und Projekt sind optional, `Claude entscheidet` ist die Voreinstellung.
Später **Sync**. Am Mac dann:

```
/jarvis
```

Sortiert alles ins Vault und sagt, was heute dran ist. `/jarvis inbox` zeigt nur,
was drin liegt, ohne zu schreiben. `/jarvis plan` plant ohne einzulesen.

## Ohne Sync

Geht auch: In der Inbox **Als Markdown kopieren** und in den Chat mit Claude einfügen.
Der Skill verarbeitet auch eingefügten Text.

## Nächste Stufen

- **3:** Morgen- und Abendmail an mich selbst, Google Kalender zweiseitig
- **4:** Anruf von einer KI-Stimme (ElevenLabs + Twilio), Änderungen live am Telefon
