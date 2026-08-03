# Weiterleitung der alten Stundenerfassung

Stand: 03.08.2026

Die Startseite dieses GitHub-Pages-Repositories leitet den bisherigen Link

`https://027123-prog.github.io/Zeiterfassung-V1/`

sofort auf die neue mobile Stundenerfassung weiter:

`https://stundeneingabe-next-gen-test.onrender.com/mobile-supabase-preview`

## Umsetzung

- Die produktive Umschaltung auf das neue System wurde zum Monatswechsel am
  03.08.2026 freigegeben.
- Nur `index.html` wird zur Weiterleitungsseite.
- `office_mail_viewer.html` und die uebrigen Bestandsdateien bleiben
  unveraendert.
- Die neue Ziel-App wurde vor der Aktivierung ueber `/api/health` geprueft.
- Die Zieladresse bleibt als sichtbarer Link erhalten, falls eine automatische
  Weiterleitung im Browser blockiert wird.

## Rueckfallebenen

`index.html` verwendet drei Rueckfallebenen:

1. `window.location.replace(...)` fuer normale Browser.
2. HTML-Meta-Refresh fuer Browser ohne ausgefuehrtes JavaScript.
3. Einen sichtbaren Link fuer den manuellen Wechsel.

## Rueckfall

Der vorherige Inhalt von `index.html` bleibt vollstaendig in der
Git-Historie erhalten. Bei Problemen kann der Weiterleitungs-Commit gezielt
zurueckgenommen und die alte Startseite erneut veroeffentlicht werden.
