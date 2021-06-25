---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.vis-inventwo/README.md
title: TR: ioBroker.vis-inventwo
hash: 6p41iJSyC7wqdCokx+COKC/ej6I7a1Oj4YSuttaWvA8=
---
![TR: Logo](../../../en/adapterref/iobroker.vis-inventwo/admin/inventwo.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.vis-inventwo.svg)
![TR: Number of Installations (stable)](http://iobroker.live/badges/vis-inventwo-stable.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.vis-inventwo.svg)
![TR: Number of Installations (latest)](http://iobroker.live/badges/vis-inventwo-installed.svg)
![TR: Dependency Status](https://img.shields.io/david/inventwo/iobroker.vis-inventwo.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/inventwo/iobroker.vis-inventwo/badge.svg)
![TR: Build status](https://ci.appveyor.com/api/projects/status/2hvs4fvfms7xhmnw?svg=true)
![TR: License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat)
![TR: Paypal Donation](https://img.shields.io/badge/paypal-donate%20%7C%20spenden-green.svg)
![TR: NPM](https://nodei.co/npm/iobroker.vis-inventwo.png?downloads=true)

TR: # ioBroker.vis-inventwo
TR: ## Schalter Widgets für den ioBroker.vis Adapter
TR: ###### .. ab v 2.0.0
TR: <table> <tr> <td><center><b>Universal</b><br><img src="widgets/vis-inventwo/img/Universal.gif"></td> <td><center><b>Multi</b><br><img src="widgets/vis-inventwo/img/Multi.gif"></td> <td><center><b>Image</b><br><img src="widgets/vis-inventwo/img/Image.png"></td> <td><center><b>Table</b><br><img src="widgets/vis-inventwo/img/Table.png"></td> </tr> <tr><td colspan=4></td></tr> <tr> <td><center><b>List</b><br><img src="widgets/vis-inventwo/img/List.png"></td> <td><center><b>Marquee</b><br><img src="widgets/vis-inventwo/img/Marquee.gif"></td> <td><center><b>Radio Button</b><br><img src="widgets/vis-inventwo/img/Radio.gif"></td> <td><center><b>Slider vertical</b><br><img src="widgets/vis-inventwo/img/Slider2.gif"></td> </tr> <tr><td colspan=4></td></tr> <tr> <td><center><b>Slider horizontal</b><br><img src="widgets/vis-inventwo/img/Slider1.gif"></td> <td><center><b>Colorslider horizontal</b><br><img src="widgets/vis-inventwo/img/ColorSliderHor.png"></td> <td><center><b>Colorslider horizontal</b><br><img src="widgets/vis-inventwo/img/ColorSliderVert.png"></td> <td><center><b>Toggle Switch</b><br><img src="widgets/vis-inventwo/img/Toggle.gif"></td> </tr> </table>

TR: ###### .. v 1.3.8
![TR: Beispiel](http://resources.inventwo.com/github/inventwo/Set.png)

TR: Mit Hilfe unserer Widgets lassen sich folgende Projekte verwirklichen. Zur Zeit befinden sich in unserem Adapter NUR die reinen Schaltflächen (siehe oben) und die Icons. Uhr und Wetter stammen aus anderen Adaptern und müssen ggf. zusätzlich installiert werden.

![TR: Beispiel](http://resources.inventwo.com/github/inventwo/Preview.png)

![TR: Beispiel](http://resources.inventwo.com/github/inventwo/Preview2.png)
---

TR: ## Unterstützung
TR: Falls Dir unsere Arbeit gefällt und Du uns unterstützen möchtest, wir freuen uns über jede Spende.

TR: (Dieser Link führt zu unserem PayPal-Konto und steht in keiner Verbindung zum ioBroker)

[![TR: Spende](http://resources.inventwo.com/github/inventwo/spende.png)](https://www.paypal.com/donate?hosted_button_id=7W6M3TFZ4W9LW)

---

TR: ## 3.0.3
TR: - Bugfix

TR: ## 3.0.2
TR: - Bugfix

TR: ## 3.0.1
TR: - Bugfix

TR: ## 3.0.0
```diff
#### ACHTUNG ####
Nach dem Update sind die Icons vom Universal- und Multiwidget
nicht zu sehen, sind aber nicht weg! Damit diese wieder zu sehen sind müssen
die Widgets einmal EINZELN im Editor angeklickt werden.
```

TR: - Beim Universal- und Multiwidget kann der Inhaltstyp geändert werden.
TR:     - Inhaltstypen: Bild (Standard), Analoge Uhr, Digitale Uhr und HTML/Text
TR:     - Analoge und digitale Uhr: Farbe des Ziffernblatts under Zeiger kann frei gewählt werden, Zeitzone kann geändert werden
TR:     - Statt dem Icon kann ein eigener Text oder ein Datenpunktwert per Binding angezeigt werden
TR: - Vergleichsoperatoren Größer-Gelich und Kleiner-Gleich
TR: - PopUp kann per Datenpunk geöffnet werden
TR: - Bugfix:
TR:     - Colorslider unsichtbar wenn für CIE kein Wert vorhanden ist
TR:     - Links funktionieren nicht im Popup
TR:     - State Rückmeldedauer funktioniert nicht richtig

TR: ## 2.9.7
TR: - Bugfix

TR: ## 2.9.6
TR: - Bugfix

TR: ## 2.9.5
TR: - Bugfix

TR: ## 2.9.4
TR: - Bugfix

TR: ## 2.9.3
TR: - Fehler mit PopUp behoben: Klick zum schließen wurde direkt nach Öffnen registriert und Klick löste Buttons hinter dem PopUp aus
TR: - Zustände wurden bei View in PopUp nicht richtig angezeigt

TR: ## 2.9.2
TR: - Problem mit Datenpunkt zum Schließen des Popups behoben. ACHTUNG! Der Datenpunkt muss erneut ausgewählt werden

TR: ## 2.9.1
TR: - Bugfix

TR: ## 2.9.0
TR: - Multi-Widget-Status können unabhängig vom Widget-Typ nach Datenpunkten oder Views prüfen
TR: - Optionen zum automatischen Schließen des Popups hinzugefügt
TR: - Bugfixes

TR: ## 2.8.3
TR: - Bugfix

TR: ## 2.8.2
TR: - Problem mit Colorslider behoben: Wert wird nicht in Datenpunkt gesetzt, wenn "Wert bei Freigabe aktualisieren" aktiviert ist",

TR: ## 2.8.1
TR: - Fehler behoben: Color Slider RGB aktualisiert bei Dp Änderung nicht (WICHTIG: Datenpunkte müssen neu ausgewählt werden!)

TR: ## 2.8.0
TR: - View in PopUp Option für Universal- und Multi-Widget hinzugefügt
TR: - Bugfix

TR: ## 2.7.11
TR: - Bugfix

TR: ## 2.7.10
TR: - Problem mit Bildern im Universal und Multi Widget behoben
TR: - Problem mit Bildwechesl im Universal und Multi Widget behoben

TR: ## 2.7.9
TR: - Option für die Bildgröße für das Image-Widget hinzugefügt
TR: - Fehler von vorheriger Version behoben

TR: ## 2.7.8
TR: - Problem mit Textausrichtung behoben
TR: - Problem mit Bildgröße im Image-Widget behoben

TR: ## 2.7.7
TR: - Problem mit der Bildgröße behoben
TR: - Problem mit dem Farbregler behoben, dass der Wert beim loslassen nicht gespeichert wurde

TR: ## 2.7.6
TR: - Problem mit Symbolfarbe für Navi-Widget behoben
TR: - Problem mit Hervorhebung auf Touch-Geräten behoben
TR: - Problem mit Radiobutton-Widget und Datentyp Zahlen behobenn

TR: ## 2.7.5
TR: - JSON Tabelle farbliche Schwellenwerte für Zahlen
TR: - Fehler beim Slider behoben wenn ungültiger Wert im Datenpunkt steht
TR: - Fehler behoben: Signalbilder wurden mit eingefärbt
TR: - Option um Bildfarbe zu invertieren eingefügt, um Farbfilter zu umgehen
TR: - Color Slider kann nun zwischen HEX, RGB und CIE unterscheiden

TR: ## 2.7.4
TR: - Fehlende Übersetzung für Hover-Farben hinzugefügt

TR: ## 2.7.3
TR: - Fehler beim Multi-State und mehreren Zuständen behoben
TR: - Schatten und Rand Hover für Buttons hinzugefügt

TR: ## 2.7.2
TR: - Fehler in Radiobutton mit Bildfarbe behoben
TR: - Fehler behoben: Doppeltes klicken bei State mit Verweildauer
TR: - Hovereffekt für Buttons eingefügt
TR: - Problem mit anzeigen des Sliderwertss behoben
TR: - Slider Text anhängen möglich

TR: ## 2.7.1
TR: - Bugfix

TR: ## 2.7.0
TR: - Neues Widget: Farbslider
TR: - JSON Tabelle Spaltenformat boolean und number
TR: - JSON Tabelle Kopfzeile kann fixiert werden
TR: - JSON Tabelle Fehler beim sortieren behoben
TR: - JSON Tabelle konfigurierbare Dummyzeile wenn JSON leer ist
TR: - Fehler behoben

TR: ## 2.6.0
TR: - Universal- & Multi-Widget Vergleichsoperatoren gleich, größer, kleiner und nicht hinzugefügt
TR: - Slider Min/Max invertieren
TR: - Slider Wert erst beim loslassen setzen
TR: - Widget um Wert zu erhöhen oder zu senken
TR: - JSON Tabelle Fehler mit Datum behoben

TR: . JSON Tabelle anzeige von Millisekunden möglich

TR: - JSON Tabelle Platzhalter wenn Eintrag leer ist
TR: - JSON Tabelle Spalten können per Klick sortiert werden

TR: ## 2.5.11
TR: - Bugfix

TR: ## 2.5.10
TR: - Bugfix

TR: ## 2.5.9
TR: - Der Prozess der Bildfarbfilterung wurde geändert
TR: - Die Bildfarbe kann jetzt ein Datenpunkt sein

TR: ## 2.5.8
TR: - Bugfix

TR: ## 2.5.7
TR: - Bugfix

TR: ## 2.5.6
TR: - Bugfix

TR: ## 2.5.5
TR: - Bugfix

TR: ## 2.5.4
TR: - Bugfix (State: doppeltes senden dese Wertes bei touch)

TR: ## 2.5.3
TR: - Grauer Kippschalter hinzugefügt

TR: ## 2.5.2
TR: - Bugfix

TR: ## 2.5.1
TR: - Bugfix

TR: ## 2.5.0
TR: - Kippschalter hinzugefügt
TR: - Bugfix

TR: ## 2.4.3
TR: - Bugfix

TR: ## 2.4.2
TR: - Bugfix

TR: ## 2.4.1
TR: - Bugfix

TR: ## 2.4.0
TR: - Randstil zur JSON-Tabelle hinzugefügt
TR: - Farbauswahö für Icons zu allen Widgets hinzugefügt
TR: - Fehlerbehebung

TR: ## 2.3.2
TR: - Fehler bei der Navigation mit dem Widget 'View in Widget' behoben

TR: ## 2.3.1
TR: - Fehler in JSON Tabelle behoben

TR: ## 2.3.0
TR: - Problem behoben, bei dem Schaltflächen zweimal Werte senden
TR: - Datum / Uhrzeit und Bildformat für Tabellenzellen hinzugefügt
TR: - Universal- und Multi-Widget-Attribute werden beim Klicken auf Widget aktualisiert

TR: ## 2.2.3
TR: - Fehler in JSON Tabelle behoben

TR: ## 2.2.2
TR: - Fehler im Multi Widget behoben: Bilder und Text wechseln nicht bei Typ Navigation

TR: ## 2.2.1
TR: - Fehler in JSON Tabelle behoben, wenn kein gültiges JSON-Objekt vorhanden ist
TR: - Fehler in Value-List behoben: Wert wird nicht aktualisiert

TR: ## 2.2.0
TR: - Datenpunktwerte werden jetzt bei allen Widgets im Editor angezeigt
TR: - Neues Widget: Marquee (Laufschrift)
TR: - Universal und Multi State Verweildauer hinzugefügt
TR: - List Widget Abstand zwischen den Einträgen kann eingestell werden

TR: ## 2.1.0
TR: - Datenpunktwerte werden im VIS Editor angezeigt!

TR: ## 2.0.1
TR: - Übersetzungsfehler behoben
TR: - Border Farbe behoben
TR: - Widget-Untertitel behoben

TR: ## 2.0.0
TR: - Switch, Button, Nav und Background Widget (sowie die kleinen Ausführungen) zu einem einzigen Widget zussammengeführt -> dem Universal Widget
TR: - Multi Widget -> wie das Universal, nur dass hier auf mehrere Datenpunkte und Werte geprüft werden kann (Ähnlich der Signalbild Funktion)
TR: - Image Widget kann nun auf Datenpunkt prüfen
TR: - Radiobuttons hinzugefügt
TR: - Werteliste hinzugefügt (Kann Liste aus einem Datenpunkt oder manuell eingetragenem Text erstellen)

TR: ## 1.3.8
TR: - Changed slider step to decimal
TR: - Fixed problem with numeric values

TR: ### 1.3.7
TR: - Fixed problem with navigation on touchscreens

TR: ### 1.3.6
TR: - Added set state option for navigation
TR: - Fixed problem with datapoints without config

TR: ### 1.3.5
TR: - Added refresh rate for table

TR: ### 1.3.4
TR: - Removed icons and backgrounds, changed config, Fixed navigation

TR: ### 1.3.3
TR: - Fixed background widget value option

TR: ### 1.3.2
TR: - Bug fix

TR: ### 1.3.1
TR: - Changed navigation button color behaviour
TR: - Added new icons

TR: ### 1.3.0
TR: - Added JSON table
TR: - Added delay for navigations
TR: - Text in buttons can now be HTML
TR: - Added new icons

TR: ### 1.2.3
TR: - Added Navigation active color
TR: - Fixed state color for value switch

TR: ## 1.2.2
TR: - Bug Fix: slider value, config

TR: ## 1.2.1
TR: - Fixed Slider Widget: seperatet into two widgets (horizontal and vertical)

TR: ### 1.2.0
TR: - Added image widget
TR: - Added Slider to change border radius for all 4 corners (If this version is an update for you, you need to click on each button in the vis-editor to get back the default corners)
TR: - Added new icons

TR: ### 1.1.1
TR: - Bug fix

TR: ### 1.1.0
TR: - Added slider widget
TR: - Added option to mirror image
TR: - Added new icons
TR: - Changed button widgets to use default font and text options

TR: ### 1.0.0
TR: - Widget background and content opacity, Switch can be changed from boolean to value, changed icons from white to black, added seamless backgrounds

TR: ### 0.1.2
TR: - Bug fixes

...

TR: ### 0.1.1
TR: - Bug fixes

...

TR: ### 0.1.0 (Erstveröffentlichung)
TR: - inventwo Design Widgets

...

TR: ### 0.0.1
TR: - Die Idee ist geboren

---

## Changelog

## License

Urheberrechte (c) 2021 [jkvarel](https://github.com/jkvarel) und [skvarel](https://github.com/skvarel) von [inventwo](https://github.com/inventwo)


MIT License (nur in englisch / englisch only)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

Icons from Icons8 https://icons8.com/