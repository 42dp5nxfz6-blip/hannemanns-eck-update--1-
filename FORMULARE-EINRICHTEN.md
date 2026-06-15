# Formulare aktivieren (E-Mail-Empfang via Formspree)

Die Formulare (Reservierung, Kontakt, Newsletter) sind bereits angebunden.
Damit dich Anfragen per E-Mail erreichen, einmalig einrichten:

## 1. Formspree-Konto anlegen
- Auf https://formspree.io kostenlos registrieren (z. B. mit deiner E-Mail).

## 2. Formular erstellen
- „New Form“ klicken, Empfänger-E-Mail eintragen (dorthin gehen die Anfragen).
- Du bekommst eine Endpoint-URL der Form: `https://formspree.io/f/ABCD1234`

## 3. URL eintragen (eine Zeile)
- Datei `assets/js/main.js` öffnen.
- Ganz oben die Zeile finden:
  ```js
  var FORMSPREE_ENDPOINT = 'https://formspree.io/f/YOUR_FORM_ID';
  ```
- `YOUR_FORM_ID` durch deine echte ID ersetzen, z. B.:
  ```js
  var FORMSPREE_ENDPOINT = 'https://formspree.io/f/ABCD1234';
  ```
- Speichern. Fertig.

## Verhalten
- **Solange `YOUR_FORM_ID` steht:** Demo-Modus – die Bestätigung wird angezeigt,
  aber es wird nichts versendet.
- **Nach Eintragen der ID:** Anfragen werden an Formspree gesendet und landen
  als E-Mail in deinem Postfach. Bei Fehlern erscheint ein Hinweis mit Telefonnummer.

## Gut zu wissen
- Die erste echte Absendung muss in Formspree einmal bestätigt werden (E-Mail-Verifizierung).
- Spamschutz ist eingebaut (verstecktes Honeypot-Feld `_gotcha`).
- Der kostenlose Formspree-Plan erlaubt eine begrenzte Anzahl Einsendungen/Monat;
  fuer mehr Formulare/Volumen gibt es kostenpflichtige Plaene.
- Alle drei Formulare nutzen denselben Endpoint. Im Betreff (`_subject`) steht,
  ob es eine Reservierung oder eine allgemeine Nachricht ist.
