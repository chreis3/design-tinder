# Design-Tinder — dauerhafte Teilnehmer-Version

Diese Teile bilden zusammen die App:

- `index.html` — die App selbst. Wird bei der Einrichtung **einmal** mit
  deinem GitHub-Namen und Repo-Namen befüllt, danach **nie wieder angefasst**.
- `images/` — Ordner mit den Bilddateien für den aktuellen Workshop.
  **Das ist ab jetzt alles, was du zwischen Workshops änderst.**
- `images.txt` — nur eine Absicherung, falls die automatische
  Ordner-Erkennung mal nicht greift. Normalerweise ignorierst du diese Datei.

Enthalten zum Testen: drei Beispielbilder (`skitour-plakat.jpg`,
`alpendorf-plakat.jpg`, `alpwiese-foto.jpg`).

## Einmalige Einrichtung

1. Auf [github.com](https://github.com) einloggen, oben rechts **"New repository"**,
   Namen vergeben (z. B. `bild-tinder`), **Public**, erstellen.
2. `index.html` öffnen (in einem Texteditor, oder direkt bei GitHub nach dem
   Hochladen mit dem Stift-Symbol bearbeiten) und ganz oben im Skript
   `REPO_OWNER` und `REPO_NAME` eintragen, z. B.:
   ```
   const REPO_OWNER = 'lukas-meier';
   const REPO_NAME  = 'bild-tinder';
   ```
   Das sind dein GitHub-Benutzername und der Repo-Name aus Schritt 1.
3. Alle Dateien/Ordner aus diesem Zip **entpacken** (nicht das Zip selbst
   hochladen!) und bei "Add file → Upload files" ins Repo ziehen, committen.
4. Unter **Settings → Pages** bei "Source" **"Deploy from a branch"** wählen,
   Branch `main`, Ordner `/ (root)`, speichern.
5. Nach ca. 1 Minute ist die Seite live unter:
   `https://<dein-github-name>.github.io/<repo-name>/`

Diese URL bleibt für immer gleich — sie kommt auf den QR-Code, den du
wiederverwendest.

## Vor jedem Workshop

1. Im `images/` Ordner die alten Bilder löschen, neue hochladen — fertig.
   **`images.txt` musst du dafür nicht anfassen.**
2. Committen. Nach ca. 1 Minute ist die Live-Seite aktualisiert.

Die App liest den Ordnerinhalt automatisch aus (über die öffentliche
GitHub-API) und zeigt alle `.jpg`/`.png`/`.webp`/`.gif`-Dateien an, die
im `images/` Ordner liegen — unabhängig von Dateinamen oder Anzahl.

## Titel pro Anlass (ohne Datei-Änderung)

Der Titel lässt sich direkt über die URL steuern, bevor du den QR-Code
erzeugst:

- `https://.../?title=Design-Tinder`
- `https://.../?title=UI-Tinder`
- `https://.../?title=Font-Tinder`
- `https://.../?title=Irgendein%20Titel` (eigener Text, Leerzeichen als `%20`)

Ohne Parameter erscheint standardmässig "Design-Tinder".

## Bildgrösse

Für schnelles Laden auf dem Handy: Bilder idealerweise unter ca. 1–2 MB
pro Datei, z. B. auf 1200–1600 px lange Kante exportiert.

## Falls die automatische Erkennung mal ausfällt

Sehr viele gleichzeitige Aufrufe (z. B. 50+ Teilnehmende im selben
WLAN) können in seltenen Fällen an ein Limit der öffentlichen
GitHub-API stossen. In dem Fall greift automatisch die Liste in
`images.txt` als Rückfalllösung — dann dort die Dateinamen eintragen,
ein Name pro Zeile.

