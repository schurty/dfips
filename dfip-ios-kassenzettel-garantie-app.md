# DFIP: iOS-App für Kassenzettel & Garantieverwaltung

## DFIP Overview
1. Requester(s): [Dein Name]
2. Reddit discussion thread (optional): [Link, falls vorhanden]
3. Proposal fee (50 DFI) txid: [txid, falls relevant]

## Kurzbeschreibung
Entwicklung einer iOS-App, mit der Nutzer Kassenzettel fotografieren, Artikel erfassen und Garantieinformationen zentral hinterlegen können. Die Kassenzettel-Bilder werden zusammen mit den Artikel- und Garantiedaten in einer Datenbank gespeichert, sodass die Garantieansprüche später schnell auffindbar sind.

## Ziele & Nutzen
- **Schneller Zugriff** auf Garantien und Belege an einem Ort.
- **Digitale Archivierung** von Kassenzetteln mit Foto/Scan.
- **Strukturierte Datenhaltung** für Produkte, Händler und Garantiefristen.
- **Verbesserte Nachweisbarkeit** bei Garantieansprüchen.

## Funktionsumfang (MVP)
1. **Kassenzettel scannen**
   - Kamera-Scan mit Zuschneiden und Bildoptimierung.
   - Speicherung der Originalbilder.
2. **Artikel erfassen**
   - Manuelle Eingabe von Artikelname, Kategorie, Kaufdatum, Preis, Händler.
   - Option: OCR-Extraktion (späterer Ausbau).
3. **Garantieverwaltung**
   - Garantiezeitraum und Ablaufdatum.
   - Erinnerungen vor Ablauf (Push Notification).
4. **Suche & Filter**
   - Suche nach Artikel, Händler oder Kategorie.
   - Filter nach Garantie-Status (aktiv/abgelaufen).

## Datenmodell (Vorschlag)
- **Receipt**
  - id, purchaseDate, merchant, totalAmount, imageURLs
- **Item**
  - id, receiptId, name, category, price, warrantyMonths, warrantyEndsAt
- **Warranty**
  - id, itemId, notes, status, reminderDate

## Technischer Ansatz (Vorschlag)
### iOS
- **Swift/SwiftUI** für UI und App-Logik.
- **VisionKit** (Document Scanner) für Belegerfassung.
- **Core Data** oder **SQLite** für lokale Speicherung.
- Optional: **Cloud Sync** (z. B. iCloud/CloudKit) für Backup und Geräte-Sync.

### Backend (optional, falls Cloud-Datenbank benötigt)
- REST API für Nutzer- und Datenverwaltung.
- Datenbank z. B. PostgreSQL (Receipts/Items/Warranties).
- Bildspeicher z. B. S3-kompatibel.

## Datenschutz & Sicherheit
- Lokale Speicherung als Default, Cloud-Sync optional.
- Verschlüsselung sensibler Daten.
- Zugriff per FaceID/TouchID möglich.

## Roadmap (grob)
1. **MVP**: Scan, Artikel erfassen, Garantieverwaltung.
2. **OCR** zur automatischen Auslese der Kassenzettel.
3. **Cloud-Sync** & Multi-Device.
4. **Export/Sharing** von Belegen für Servicefälle.

## Offene Fragen
- Soll eine Cloud-Synchronisierung zwingend sein oder optional?
- Welche Plattformen sollen langfristig unterstützt werden (Android/Web)?
- Gibt es Präferenzen für ein Backend oder lokale-only Lösung?

<!--
Non-obligation:
I understand that vote of confidence for DFIP carries no obligations by any developers to implement the proposals. DeFiChain is a community projects. Pull requests can be submitted by community and reserved to be evaluated for safety and general community acceptance.
-->
