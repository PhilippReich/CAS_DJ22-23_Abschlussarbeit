# CAS_DJ22-23_Abschlussarbeit
Dokumentation der Abschlussarbeit für den CAS Datenjournalismus 2022/23

# Transfer-Analyse – so sehr Ausbildungsliga ist die Super League wirklich

![Teaserbild](https://github.com/PhilippReich/CAS_DJ22-23_Abschlussarbeit/blob/main/Teaserbild.jpg)

## 0 Checkliste

- These formulieren: **Die Super League ist keine echte Ausbildungsliga – nur ein Bruchteil aller Transfers haben eine Top-5-Liga als Ziel**
- These checken: Relevanz? Neu? Aufwand/Ertrag? **Thema ist aktuell, das Wintertransferfenster schliesst Anfang Februar. Ähnliche Storys gab es bislang nur zu ausländischen Ligen. Aufwand ist machbar.**
- Knackpunkt bestimmen. **Abgleichen der Zielvereine mit der jeweiligen Ligahöhe. Stimmt die These überhaupt? Was, wenn nicht?**
- Briefing Person konsultieren: **War in meinem Fall nicht nötig.**
- Daten beschaffen/reinigen/analysieren/visualisieren -> These justieren **Um einen int. Vergleich zu erhalten, müssen die Transfer-Daten von vergleichbaren Ligen beschafft werden.**
- Dokumentieren Code und statistische Annahmen: **Siehe Github-Repository.**
- Link auf Publikation: **Siehe weiter unten.**
- Aufwandslogbuch: **Siehe weiter unten.**

## 1 Daten-Quelle
Um an den benötigten Datensatz zu kommen, habe ich alle Super-League-Transfers (nur die Abgänge) seit der Saison 2003/04 auf [transfermarkt.ch](https://www.transfermarkt.de/super-league/transfers/wettbewerb/C1/plus/?saison_id=2003&s_w=&leihe=0&intern=0) gescraped. Warum gerade diese Saison? Seither besteht die oberste Schweizer Fussball-Liga konstant aus 10 Klubs, zuvor waren es jeweils 12. Ausserdem beträgt der Zeitraum der Analyse so genau 20 Saisons. Das grösste Problem bei der Datenbeschaffung ([Hier der Link zum kommentierten Python-Notebook](https://github.com/PhilippReich/CAS_DJ22-23_Abschlussarbeit/blob/main/2023_CAS_Abschlussarbeit_Transfers_Super_League.ipynb)) war, dass beim Scrapen der Transfers zwar ein Zielland eruiert werden konnte, nicht aber die genaue Ligahöhe, in welcher der Klub zum Transferzeitpunkt spielte. Über die Klub-IDs konnte ich allerdings die [historischen Ligaplatzierungen aller aufnehmenden Vereine bei transfermarkt.ch](https://www.transfermarkt.de/-/platzierungen/verein/79) scrapen und die so entstandenen Resultate mit dem ursprünglichen Dataframe mergen.

## 2 Daten-Analyse
Die 1751 Super-League-Abgänge konnte ich mit der Python-Bibliothek Pandas in der Folge schnell kategorisieren, allerdings bemerkte ich, dass die erhaltenen Resultate nur schwer einzuordnen sind. Sind 186 Top-5-Transfer von 1751 Gesamt-Transfers nun eine gute Quote oder nicht? Ein Vergleich zu anderen Ausbildungsligen Europas drängte sich deshalb auf: Der Python-Code zur Super League liess sich glücklicherweise problemlos auf die 11 ausgewählten Ligen anpassen (nur der Ausgangslink musste geändert werden) und so erhielt ich mit relativ wenig Aufwand den benötigten Vergleich ([hier die Resultate der anderen Ligen](https://github.com/PhilippReich/CAS_DJ22-23_Abschlussarbeit/tree/main/Transfers_andere_Ligen)). Zu berücksichtigen galt es lediglich, dass es sich bei den anderen Ligen nicht wie bei der Super League um 10er-Ligen handelt, weshalb ich nicht die absoluten Zahlen, sondern die Quote aller Top-5-Transfers für die Visualisierung heranziehen musste.

## 3 Visualisierung
Da bei watson.ch keine Spezialisten aus dem Bereich DataViz arbeiten, beschloss sich die Visualisierungen mithilfe von Datawrapper zu realisieren. Als besonders herausfordernd entpuppte sich das schon vor Beginn der Arbeit gesetzte Ziel einer Karte mit Transferlinien in jedes Zielland. Hierfür mussten auf [geojson.io](https://geojson.io/#map=2.01/7.83/19.4) zunächst alle Verbindungslinien im GEOJSON-Format gezeichnet und dann in Datawrapper importiert werden. Leider war die [so entstandene Karte](https://www.datawrapper.de/_/kJ9PU/) nicht zoombar, weshalb ich mit zwei Reitern («Europa» und «Rest der Welt») arbeiten musste. Bei den restlichen Visualisierungen gab es mit Datawrapper keinerlei Probleme.

## 4 Artikel
[Publikation auf watson.ch](Hier kommt der Link rein)

## 5 Aufwandslogbuch
- Datenbeschaffung/Programmieren: 24 Std.
- Datenreinigung: 6 Std.
- Daten-Analyse und Überdenken der These: 4 Std.
- Visualisierung: 6 Std.
- Texten: 4 Std.
- TOTAL: 44 Std.
