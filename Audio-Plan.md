# Nightfall — Ton, Stimmen, Bildschirme

Antworten auf die drei Fragen, plus der Plan dahinter. Nichts davon blockiert das Bauen — alles
kann nachträglich rein, weil Untertitel und `AudioSource` getrennt sind.

---

## 1. Wie kommen wir an die Voicelines?

Es gibt drei Wege. Ich empfehle **B für den Prototyp, A für die Fassung, die jemand spielt.**

### A — Echte Sprecher (die richtige Antwort für das fertige Spiel)
Das Drehbuch hat sechs sprechende Figuren. Cabert, Okonkwo und Halvorsen tragen praktisch alles,
die zwei Handlanger und die Nachrichtensprecherin sind je unter zwanzig Zeilen.

- **Fiverr / Voice123 / Bodalgo** — deutschsprachige Sprecher, 3–8 € pro Minute Rohmaterial.
  Für Prolog + Mission 1 sind das ca. 6 Minuten, also 30–60 € pro Rolle.
- Bodalgo ist deutsch und hat die besseren Sprecher; Fiverr ist billiger und schneller.
- Was du lieferst: das Drehbuch als Tabelle, eine Zeile pro Datei, mit Dateinamen
  (`M01_Handlanger1_03.wav`) und einer Regieanweisung in einem Satz.
- Was du zurückbekommst: WAV, 48 kHz, trocken (ohne Hall). Den Raumklang machen wir in Unity,
  sonst klingt die Wohnung wie das Wohnzimmer des Sprechers.

### B — KI-Stimmen (jetzt sofort, kostenlos bis günstig)
- **ElevenLabs** — mit Abstand die beste deutsche Sprachsynthese. Kostenlos 10 000 Zeichen/Monat,
  5 $/Monat für 30 000. Prolog + Mission 1 sind zusammen unter 4 000 Zeichen. Reicht also gratis.
- Stimme pro Figur einmal wählen und die ID notieren, sonst klingt Cabert in Mission 3 anders als
  im Prolog.
- **Wichtig:** ElevenLabs' Lizenz erlaubt kommerzielle Nutzung ab dem bezahlten Tarif, im
  Gratistarif nur mit Namensnennung. Für einen Release also mindestens den 5-$-Tarif.

### C — Convai (hast du schon)
Du hast **Convai NPC AI Engine** im Projekt. Das ist für *freie* Gespräche gedacht — NPC antwortet
live auf das, was der Spieler sagt. Für ein geschriebenes Drehbuch ist das der falsche Weg: du
willst genau diese Zeilen, in genau dieser Reihenfolge. Convai wäre interessant für Passanten und
Informanten in den Nebenaufgaben, nicht für die Story.

### Wie es ins Spiel kommt
`CaptionStep` hat pro Zeile Sprecher, Text und Dauer. Es fehlt nur ein Feld `AudioClip clip` und
zwei Zeilen Code, die es abspielen und die Dauer aus der Cliplänge nehmen statt aus der Zahl.
Sag Bescheid, dann baue ich das — dann fällt auch das Zahlenraten bei `seconds` weg.

---

## 2. Wie kriege ich ein Bild auf den Fernseher, und welches?

**Das läuft schon.** `TVScreen` auf `TV_Apt_01/Screen` spielt vier gerenderte Nachrichtenbilder
(`Assets/Nightfall/Art/Generated/NF_TV_Screen_0..3.png`) und schneidet alle ~3 Sekunden um, mit
einer flackernden Leuchte davor, die den Raum blau färbt.

Die vier Bilder sind ein Nachrichtenstudio mit Laufband, Lower Third und der Schlagzeile, die in
der Szene gesprochen wird — *EINBRUCH IN DIE ZENTRALBANK*, *ZWEI TAGE UNBEMERKT*,
*ZWÖLF MILLIONEN VERSCHWUNDEN*, *HALVORSEN: BEDAUERLICHER EINZELFALL*.

### Eigene Bilder einsetzen
Ein Bild ins Projekt ziehen, im Importer **sRGB** an, dann im Inspector von `Screen` in die Liste
`Frames` legen. Fertig.

Ein Haken: das TV-Mesh hat verdrehte UVs — `uv.x` läuft *senkrecht* über nur 0…0,586, `uv.y`
waagerecht von rechts nach links. Ein normal orientiertes Bild erscheint darauf gedreht und
gespiegelt. Die vier vorhandenen Bilder sind schon entsprechend umgerechnet. Wenn du eigene
einsetzen willst, sag Bescheid — der Umrechner steckt in dem Editor-Skript, das die vier gebaut
hat, und ich mache daraus einen Menüpunkt.

### Echtes Video statt Standbildern
Geht auch, kostet aber Speicher und CPU:
1. `.mp4` (H.264, 1280×720 reicht) ins Projekt.
2. `RenderTexture` 1024×1024 anlegen.
3. `VideoPlayer` auf das TV-Objekt, Render Mode **Render Texture**, Clip und Target zuweisen.
4. Diese RenderTexture als einzelnen Eintrag in `Frames` — `TVScreen` nimmt jede `Texture`.

Für den Prolog sind Standbilder besser: sie kosten nichts, laufen auf jeder Maschine gleich, und
aus sechs Metern Entfernung in einem dunklen Zimmer sieht niemand den Unterschied.

---

## 3. Longterm: welche Soundeffekte?

Nach Wichtigkeit sortiert. Die ersten beiden Blöcke sind der Unterschied zwischen „Prototyp" und
„Spiel"; alles danach ist Politur.

### Block 1 — Die Dinge, die der Spieler selbst auslöst (ohne die fühlt sich nichts an)
| Was | Anzahl | Hinweis |
|---|---|---|
| Schritte | 4–6 Varianten × 5 Untergründe (Parkett, Beton, Kies, Metall, Asphalt) | Randomisiert, sonst hört man die Schleife nach zehn Schritten |
| Sprung / Landung | 2 + 3 (leicht, normal, hart) | Landung nach Fallhöhe skalieren |
| Enterhaken | Abschuss, Einschlag, Seil-Sirren im Schwung (Loop), Kappen | Das Sirren ist der wichtigste Sound im ganzen Spiel |
| Gleiten | Stoffrauschen, Loop, Lautstärke nach Geschwindigkeit | |
| Schlag / Treffer / Kontern | je 3 | |
| `[E]`-Interaktion | 1 Klick | Ein kurzer, trockener Klick, kein „Ding" |
| Menü / Karte auf und zu | 2 | |

### Block 2 — Die Stadt (macht aus Geometrie einen Ort)
| Was | Hinweis |
|---|---|
| Straßen-Ambience (Loop) | Verkehr, entfernte Hupen, ein Tonband für Tag, eins für Nacht |
| Dach-Ambience (Loop) | Wind, viel dünner, weit weniger Verkehr — der Kontrast verkauft die Höhe |
| Innen-Ambience | Kühlschrankbrummen, Heizung, gedämpfte Straße durchs Fenster |
| Regen | hast du schon als VFX, Ton fehlt — Loop plus Prasseln auf Blech für die Dächer |
| Vorbeifahrende Autos | 3–4 Doppler-Samples, vom `TrafficSystem` ausgelöst |

### Block 3 — Die Erzählung
- **Mentalisten-Sicht:** ein Ein- und ein Ausschaltton, dazu ein tiefer Loop, solange sie an ist.
  Beim Scannen ein Ticken, das mit dem Ring schneller wird, und ein Ton beim Schließen.
- **Missionsziel erreicht / neues Ziel:** zwei sehr kurze, sehr leise Töne. Nicht mehr.
- **Telefon:** Klingeln, Mailbox-Piep, Auflegen.
- **Türen:** aufschließen, Klinke, zufallen. Bei uns unter dem Schwarzbild — der Ton *ist* die Tür.

### Block 4 — Musik
Der Prolog braucht **keine**. Das ist Absicht: ein Fernseher in einem dunklen Zimmer und sonst
nichts. Die erste Musik im Spiel sollte das erste Mal sein, dass Cabert den Enterhaken benutzt.

Danach: ein ruhiges Thema für die Wohnung, ein pulsierendes für die Verfolgung, ein Klavierthema
für Okonkwo. Drei Stücke reichen für die ersten drei Missionen.

### Woher
- **freesound.org** — CC0, gut für Ambience und Alltagsgeräusche, Qualität schwankt.
- **Sonniss GDC Bundle** — jedes Jahr gratis, mehrere hundert GB professionell aufgenommen,
  lizenzfrei auch kommerziell. Der beste Deal im Audio.
- **Asset Store: „Universal Sound FX"** oder **„Footsteps Essentials"** — fertig sortiert,
  ca. 20–30 €, spart einen ganzen Tag Suchen.
- Musik: **Epidemic Sound** (Abo) oder ein Komponist auf Fiverr, 80–150 € pro Stück.

### Was ich brauche, um es einzubauen
Einen Ordner `Assets/Nightfall/Audio/` mit Unterordnern `Steps`, `Player`, `World`, `UI`, `Voice`.
Leg rein, was du hast — ich baue dann einen `AudioDirector`, der Ambience nach Innen/Außen und
Tag/Nacht blendet, und hänge die Einzelsounds an die Systeme, die sie auslösen.

**Reihenfolge, wenn du nur eine Sache machst:** Schritte. Nichts sonst verändert das Spielgefühl
so stark für so wenig Arbeit.
