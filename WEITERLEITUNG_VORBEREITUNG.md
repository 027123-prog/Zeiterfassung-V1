# Weiterleitung der alten Stundenerfassung

Stand: 11.08.2026

Die Startseite dieses GitHub-Pages-Repositories ist der bekannte Stundenlink:

`https://027123-prog.github.io/Zeiterfassung-V1/`

Produktiv leitet `main` derzeit weiterhin auf die oeffentliche mobile
Stundenerfassung:

`https://stundeneingabe-next-gen-test.onrender.com/mobile-supabase-preview`

Auf dem Vorbereitungsbranch wird als neues Ziel das geschuetzte
Mitarbeiterportal hinterlegt:

`https://stundeneingabe-next-gen-test.onrender.com/mitarbeiter`

Wer dort keine gueltige Sitzung besitzt, wird von der Anwendung automatisch
nach `/mitarbeiter-login` gefuehrt. Bereits angemeldete Mitarbeiter landen
direkt bei der Erfassung mit ihrer Monatsansicht.

## Freigabebedingungen

Den Vorbereitungsbranch nicht in `main` uebernehmen, bevor alle folgenden
Punkte erfolgreich abgeschlossen sind:

1. Mitarbeiterportal in `Zeiterfassung-Next-Gen` nach `main` uebernehmen und
   das Render-Deployment abwarten.
2. Migration `010_employee_login.sql` nach ausdruecklicher Freigabe live
   anwenden.
3. Alle zwoelf aktiven Mitarbeiterkonten transaktional aktivieren.
4. Login, persoenliche Monatsansicht, Tagesansicht und Abmeldung mit einem
   echten Mitarbeiterkonto pruefen.
5. Das dokumentierte Parallel-Schreibrisiko beheben oder bewusst akzeptieren.

Bis dahin bleibt die produktive GitHub-Pages-Weiterleitung unveraendert.

## Umsetzung

- Nur `index.html` wird zur Weiterleitungsseite.
- `office_mail_viewer.html` und die uebrigen Bestandsdateien bleiben
  unveraendert.
- Die Zieladresse bleibt als sichtbarer Link erhalten, falls eine automatische
  Weiterleitung im Browser blockiert wird.
- In `index.html` muessen Meta-Refresh, Canonical-Link, JavaScript-Weiterleitung
  und sichtbarer Link immer dasselbe Ziel enthalten.

## Rueckfallebenen

`index.html` verwendet drei Rueckfallebenen:

1. `window.location.replace(...)` fuer normale Browser.
2. HTML-Meta-Refresh fuer Browser ohne ausgefuehrtes JavaScript.
3. Einen sichtbaren Link fuer den manuellen Wechsel.

## Rueckfall

Bei Problemen wird der bekannte Stundenlink wieder auf den zuletzt stabilen
oeffentlichen Mobilweg gesetzt:

`https://stundeneingabe-next-gen-test.onrender.com/mobile-supabase-preview`

Der vorherige Inhalt von `index.html` bleibt ausserdem vollstaendig in der
Git-Historie erhalten.
