# BaKo für Claude

BaKo ist eine Plattform für digitale Baustellenkoordination in Österreich. Dieses Plugin verbindet Claude (claude.ai, Desktop, Cowork, Claude Code) mit BaKo. Es besteht aus dem Konnektor `https://bako.co.at/mcp` und der Arbeitsanleitung `bako-baustelle`.

## Verwenden

Plugin hinzufügen, im Reiter „Connectors“ BaKo verbinden und mit dem eigenen BaKo-Konto anmelden. Danach zum Beispiel fragen: „Welche Termine hat das Projekt Berghotel nächste Woche?“, „Wie viel Beton ergibt die Massenermittlung Rohbau EG?“ oder „Leg einen Protokollentwurf für die Baubesprechung von heute an“.

## Daten

Claude ruft BaKo-Werkzeuge über `bako.co.at/mcp` auf. Jede Anfrage läuft mit dem Anmeldetoken des Nutzers gegen die BaKo-Datenbank, die Projekt-, Firmen- und Modulrechte prüft. Das Plugin speichert selbst nichts. Den Zugriff entzieht man unter `bako.co.at/ki-verbindungen`; das Entfernen des Konnektors allein entzieht ihn nicht. Mehr: https://bako.co.at/ki-assistenten, Datenschutz: https://bako.co.at/datenschutz.

## In English

BaKo is a construction-site coordination platform for Austria. This plugin connects Claude to BaKo through the remote MCP server `https://bako.co.at/mcp` and adds the skill `bako-baustelle`, which explains how to work with BaKo projects. Users sign in with their own BaKo account via OAuth. Claude can read projects, schedules, tasks, protocols, meetings, documents, quantity take-offs and plan measurements, bills of quantities, costs, tenders and invoices, and create drafts on request. It cannot publish, send protocols, invitations or messages, award, approve, pay or change access; creating or changing tasks triggers the same automatic task emails as in the app. Requests run with the user's own permissions; the plugin stores nothing. Revoke access at `bako.co.at/ki-verbindungen`; removing the connector alone does not revoke it. Support: support@bako.co.at.

## Lizenz / License

Die Plugin-Dateien stehen unter der MIT-Lizenz (siehe `LICENSE`). Name und Logo von BaKo sind davon ausgenommen. The plugin files are MIT-licensed (see `LICENSE`); the BaKo name and logo are excluded.

## Herausgeber / Publisher

Ing. Heinz Wucherer (Baumanagement Heinz), Urichstraße 100, 6500 Landeck, Österreich · support@bako.co.at · Nutzungsbedingungen / Terms: https://bako.co.at/nutzungsbedingungen
