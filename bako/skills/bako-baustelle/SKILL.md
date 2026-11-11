---
name: bako-baustelle
description: Arbeiten mit BaKo (Baustellenkoordination). Verwenden, wenn der Nutzer nach seinen BaKo-Projekten, Terminen, Aufgaben, Protokollen, Baubesprechungen, Plänen, Massen (Beton, Schalung, Aushub, Fenster, Treppen), LV-Positionen, Kosten, Nachträgen, Vergaben oder Rechnungen fragt oder einen Protokoll-, Besprechungs- oder Aufgabenentwurf diktiert.
---

# BaKo-Werkzeuge

BaKo ist eine österreichische Plattform für Baustellenkoordination. Der BaKo-Konnektor (`bako.co.at/mcp`) arbeitet immer mit den aktuellen Rechten des angemeldeten BaKo-Kontos. Was das Konto in BaKo nicht sehen darf, liefert auch der Konnektor nicht.

## Ablauf

1. Projekt klären: `bako_list_projects` aufrufen und mit dem Projektcode weiterarbeiten. Bei mehreren passenden Projekten nachfragen.
2. Vor jeder Änderung den aktuellen Stand lesen (zum Beispiel `bako_get_tasks`, `bako_get_schedule`, `bako_get_protocol`, `bako_get_lv_position_detail`) und Kennungen und Revisionen aus dieser Antwort verwenden.
3. Schreiben nur auf ausdrücklichen Wunsch, und vorher kurz zusammenfassen, was gespeichert wird. Es entstehen immer Entwürfe: Nichts wird veröffentlicht, versendet, vergeben, freigegeben oder bezahlt.
4. Nichts erfinden: keine Orte, Fristen, Mengen, Preise, Firmen oder Personen. Fehlt eine Pflichtangabe, gezielt nachfragen. Bei mehrdeutigen Personen die Auswahl aus `bako_search_project_people` anbieten.

## Massenermittlung und Plan-Messplatz

- `bako_list_mass_calculations` zeigt, ob eine Berechnung ein Rechenblatt mit Plan hat (`workbook`).
- `bako_get_plan_quantities` ohne `kind` liefert die Summen. Mit `kind` kommen die Einträge: `components` (Bauteile samt Schalung), `excavations` (Aushub), `windows`, `stairs`, `attributeGroups`, `markings`.
- `bako_get_mass_calculation` liefert bei Rechenblättern die Zellen mit dem von BaKo berechneten Wert.
- Werte unverändert mit Einheit wiedergeben (m, m², m³). Bei `problem` den Hinweis nennen und keinen Ersatzwert schätzen.

## Kosten

Kostenübersicht, Aufträge, Nachträge und Zahlungen (`bako_get_cost_overview`, `bako_get_order_details`) sieht nur die Projektleitung, Bauträger sehen eine gefilterte Sicht. Beträge sind EUR; Rechnungen brutto, sonst netto. Eine Rechnungsvorschau (`bako_prepare_award_invoice`) speichert nichts.

## Grenzen

Veröffentlichen, Versenden, Vergeben, Rechnungsfreigabe, Zahlungen und Projektzugänge gehen nur in der BaKo-App. Den Zugriff entzieht der Nutzer unter `bako.co.at/ki-verbindungen`.
