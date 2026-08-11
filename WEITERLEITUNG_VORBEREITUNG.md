# Weiterleitung der alten Stundenerfassung

Stand: 11.08.2026

Die Startseite dieses GitHub-Pages-Repositories ist der bekannte Stundenlink:

`https://027123-prog.github.io/Zeiterfassung-V1/`

Sie leitet nach der Freigabe direkt auf das geschuetzte Mitarbeiterportal:

`https://stundeneingabe-next-gen-test.onrender.com/mitarbeiter`

Wer dort keine gueltige Sitzung besitzt, wird automatisch zur Anmeldung
gefuehrt. Bereits angemeldete Mitarbeiter landen direkt bei der
Stundenerfassung.

## Umsetzung

- Nur `index.html` dient als Weiterleitungsseite.
- Die uebrigen Bestandsdateien bleiben unveraendert.
- Meta-Refresh, Canonical-Link, JavaScript-Weiterleitung und sichtbarer Link
  zeigen auf dasselbe Ziel.
- Ein sichtbarer Link bleibt erhalten, falls die automatische Weiterleitung im
  Browser blockiert wird.

## Rueckfall

Die vorherigen Fassungen von `index.html` bleiben in der Git-Historie
erhalten. Ein Zuruecksetzen der Weiterleitungsseite aendert ausschliesslich den
ersten Aufrufweg; die Zugriffsregeln der Zielanwendung bleiben davon
unberuehrt.
