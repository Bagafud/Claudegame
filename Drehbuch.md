> **Überholt am 25.09.2026.** Die gültige Fassung der Story steht in `Nightfall-Story.md`. Diese Datei bleibt nur als Archiv.

# NIGHTFALL — Drehbuch

Ausgebaut aus `Story roter faden.txt`. Die Prämisse, die Figuren, der Twist und alle acht Missionen
sind deine. Ergänzt habe ich: Szenengliederung, Dialog, Übergänge, die fehlenden Akt-2-Beats und
drei Korrekturen, die unten offen benannt sind.

---

## Figuren

**CABERT** — Ermittler der Stadtpolizei Nightfall. Mitte dreißig, übermüdet, überqualifiziert. Liest
Menschen und Räume wie andere Leute Schrift. Kurz vor dem Wechsel zu einem Bundesdienst. Weiß
nicht, dass er nachts jemand anderes ist.

**DIE NACHT** — dieselbe Person. Nie mit eigenem Gesicht gezeigt, nur als Handschrift, als Planung,
als Stimme im Funk am Ende. Sie ist nicht wahnsinnig. Sie ist besser.

**DIREKTOR HALVORSEN** — Polizeichef. Väterlich, langsam, freundlich. Von Bagafud gekauft. Der
Spieler soll ihn mögen, bis er es nicht mehr kann.

**MIRA OKONKWO** — Detective, Kollegin. Unbestechlich, schnell, die Einzige die Cabert wirklich
anschaut. Sie ist die Figur, die in Mission 6 die Schlinge zuzieht. Ihre Existenz macht das Ende
teuer.

**DIE ZWEI HANDLANGER** — namenlos, Gang-Members-Pack. Sie kennen ihren Boss nicht. Das ist der Witz.

**BAGAFUD INC.** — Konzern, Rüstungszulieferer, kontrolliert mehr von Nightfall als die Stadt selbst.

---

## Struktur

| | Tag / Nacht | Spielst du | Kern |
|---|---|---|---|
| **Prolog** | Abend → Morgen | Cabert | Anlernen: Sehen, Greifen, Bewegen |
| **M1 Der Fingerabdruck** | Tag | Cabert | Ermitteln. Die Nachricht. |
| **M2 Nachtschicht** | Nacht | Die Nacht | Erste Fahrverfolgung |
| **M3 Datenraub** | Nacht | Die Nacht | Erste Schießerei |
| **M4 Schatten im Revier** | Tag | Cabert | Stealth ohne Waffe |
| **M5 Konvoi-Kollaps** | Nacht | Die Nacht | Große Action |
| **M6 Die Schlinge** | Tag | Cabert | Flucht, keine Gegenwehr |
| **M7 Point of No Return** | Tag, Regen | Beide | Der Heist |
| **M8 Der Verrat** | — | Niemand | Das Ende |

**Dazwischen (neu):** drei kurze Zwischenmissionen, die Akt 2 füllen — siehe unten unter
*Die Lücke*.

---

# PROLOG — „Zwei Tage später"

### Szene 1 — Der Bericht

*Innen. Caberts Wohnung. Abend. Ein Fernseher, sonst dunkel.*

Cabert sitzt. Der Fernseher läuft. Er sieht nicht hin — er sieht durch ihn hindurch.

> **NACHRICHTENSPRECHERIN:** „…der Einbruch in die Zentralbank wurde erst nach zwei Tagen bemerkt.
> Zwei Tage. Die Ermittler sprechen von einer Handschrift, die sie so noch nie gesehen haben."
>
> „Die Täter haben keine Spuren hinterlassen. Keine Fingerabdrücke, keine Aufnahmen, kein Alarm.
> Der entwendete Betrag wird auf zwölf Millionen geschätzt."
>
> „Direktor Halvorsen sprach heute von einem, Zitat, bedauerlichen Einzelfall."

Cabert lacht einmal, kurz, ohne Freude.

> **CABERT:** „Einzelfall."

**Was du spielst:** Nichts. Vier Zeilen Untertitel, der Fernseher flackert, die Kamera steht still.
Nach zwölf Sekunden erscheint unten: **[E] Aufstehen**.

**Warum so:** Das Spiel fängt nicht mit einer Tat an, sondern mit einem Mann, der sie im Fernsehen
sieht. Beim zweiten Durchspielen ist dieselbe Szene ein Geständnis.

### Szene 2 — Schlafen

Du stehst auf. Ziel: **Geh ins Bett.**

Der Weg führt an einem Spiegel vorbei. Du kannst ihn anschauen — dann steht da nur:
*Du siehst müde aus.* Kein Effekt, keine Musik. Es ist nur wahr.

Am Bett: **[E] Schlafen**. Bild schwarz. Zwei Sekunden Stille.

**Technik:** `PoseStep` mit `Lying Down`, dann `ScreenOverlay.SnapBlack()`.

### Szene 3 — Morgen

Bild kommt zurück, zu hell. Du stehst neben dem Bett, nicht darin.

> **SYSTEM:** *1 verpasster Anruf — Okonkwo*

**[E] Abhören:**

> **OKONKWO (Mailbox):** „Cabert. Ich weiß, du hast frei. Ich weiß auch, dass dich das noch nie
> gestört hat. Dächer nördlich der Zentralbank. Halvorsen will es schnell, ich will es richtig.
> Komm einfach."

Ziel: **Geh zur Zentralbank.** Der Wegpunkt erscheint auf der Karte.

### Szene 4 — Der Weg hinauf

Vor der Haustür. Die Stadt ist laut und hell und interessiert sich nicht für dich.

Am Zielgebäude: **Tutorial Enterhaken.** Erst ein Hinweis, dann darf man es selbst.

> **HINWEIS:** *Rechte Maustaste — Ankerpunkt anvisieren*
> *Rechte Maustaste erneut — Zugreifen*
> *Leertaste im Schwung — Loslassen*

Oben angekommen endet der Prolog. Keine Cutscene, nur ein Schnitt auf den Missionstitel:

> **DER FINGERABDRUCK**

**Was der Prolog leisten muss:** Bewegen, Greifen, Interagieren, Karte lesen. Vier Dinge, keine
Erklärtexte länger als eine Zeile.

---

# MISSION 1 — Der Fingerabdruck

*Tag. Dächer über dem Bankenviertel.*

### Szene 1 — Der Tatort von oben

Okonkwo wartet nicht. Sie hat eine Nachricht am Anker hinterlassen — ein Zettel, beschwert mit
einem Kaffeebecher.

> *„Die Kollegen sagen, er ist über die Dächer weg. Die Kollegen sagen viel. — M."*

**Was du spielst:** Erste Nutzung der **Mentalisten-Sicht [V]**. Die Welt entsättigt, Hinweise
glimmen gelb. Drei Spuren auf diesem Dach:

1. Ein Abrieb an der Brüstungskante — *jemand ist hier angeseilt gewesen.*
2. Ein Schraubenrest, magnetisch — *kein Baumaterial. Ausrüstung.*
3. Ein Fußabdruck im Kiesdach, halb ausgewischt — *er hat aufgeräumt. Nicht gut genug.*

Jeder Hinweis scannt per **[E]**, der Fokuskreis schließt sich, Text ploppt auf. Nach dem dritten
öffnet sich die Spur: eine Linie über vier Dächer.

### Szene 2 — Die Verfolgung

Grapple und Parkour über vier Dächer. Keine Gegner. Kein Zeitdruck. Die Stadt von oben, einmal
ohne Bedrohung — damit sie später etwas bedeutet.

Am Ende: ein Dachfenster, darunter Licht.

### Szene 3 — Das Belauschen

**[E]** — ducken. Kamera geht ins Halbdunkel, Ton wird gefiltert.

> **HANDLANGER 1:** „Er sagt, wir fassen nichts an. Wir tragen nur."
> **HANDLANGER 2:** „Ich hab ihn nie gesehen. Du?"
> **HANDLANGER 1:** „Niemand hat. Der Typ, der die Zentralbank gemacht hat, zeigt sein Gesicht nicht."
> **HANDLANGER 2:** „Zwölf Millionen und er will immer noch mehr."
> **HANDLANGER 1:** „Er will nicht mehr Geld. Er will was aus dem Turm."

Sie gehen. Du folgst ihnen **nicht** — das Spiel lässt dich, aber das Ziel sagt: *Sieh dir die
Tafel an.*

### Szene 4 — Die Planungstafel

Eine Wand voller Fotos, Linien, Zeitangaben. **[E]** zum Untersuchen, dreimal:

1. **Das Ziel:** Bagafud Inc., Hauptkomplex. Grundriss, Wachwechsel, Lüftungsschächte.
2. **Die Fracht:** ein Datenblatt. Ein Virus. Keine Tiere, keine Pflanzen, keine Gebäude. Nur
   Menschen. Reichweite: Kontinente.
3. **Die Handschrift.**

> **UI:** *Handschriftvergleich läuft…*
> *Übereinstimmung: 99,8 %*
> *Vergleichsprobe: nicht in der Datenbank*

**Korrektur zum Original:** Hier stand „99,8 % (Cabert)". Das nimmt dem Spieler den Schluss weg.
So zieht er ihn selbst — und weiß trotzdem, was er weiß.

Cabert sagt nichts. Er fotografiert nichts. Er geht.

### Szene 5 — Nach Hause

*Abend.* Der Weg zurück ist der einzige Moment im Spiel, in dem nichts passiert. Das ist Absicht.

In der Wohnung, Cutscene beim Eintreten:

Cabert legt das Handy auf den Tisch. Öffnet die Notizen. Tippt. Legt es hin, Display nach oben, so
dass es beim Entsperren sofort aufgeht.

> *„Ich weiß, dass du das liest.
> Ich will wissen, was in dem Turm ist.
> Ich will es von dir hören, nicht von einer Tafel."*

Er geht ins Bett. Schwarz.

**Ziel erreicht.**

---

# MISSION 2 — Nachtschicht

*Nacht. Dieselbe Wohnung. Dieselbe Person.*

### Szene 1 — Die Antwort

Bild kommt zurück — aber die Farben stimmen nicht. Kälter. Der Kontrast höher. Der Bass setzt ein.

Du stehst am Tisch. Das Handy liegt da. **[E]:**

> *„Ich lese alles, was du schreibst.
> Im Turm liegt etwas, das niemand besitzen darf.
> Deshalb hole ich es.
> Schlaf weiter, Cabert."*

Du — nicht Cabert, **du** — tippst eine Antwort. Der Spieler hat keine Wahl, welche.

> *„Dann brauchst du ein Auto."*

### Szene 2 — Der Wagen

Ziel: **Besorg ein Fluchtfahrzeug.**

Erstes GTA-Gameplay. Ein getunter Wagen steht in einer Seitenstraße. Kein Schloss, kein Minispiel —
die Nacht kann das einfach.

Zwanzig Sekunden später: Blaulicht.

### Szene 3 — Die Jagd

Zwei Streifenwagen. Enge Straßen, Ampeln, Gegenverkehr. Kein Waffengebrauch — die Nacht tötet keine
Polizisten. Nicht aus Moral. Weil es Aufmerksamkeit kostet.

Abhängen, dann in die Garage. Tor zu. Motor aus. Stille.

**UI & Gefühl:** Die Minimap wird nachts kälter und enger, der Sichtkegel der Streifenwagen
erscheint rot. Der Soundtrack ist durchgehend Bass, keine Melodie.

---

# MISSION 3 — Datenraub

*Dieselbe Nacht, drei Stunden später. Sub-Labor von Bagafud, Industrieviertel.*

### Szene 1 — Rein

Stealth. Drei Wachen, ein Zaun, eine Kamera. **Takedowns von hinten mit [F]**. Keine Waffe gezogen.

### Szene 2 — Die Karte

Im Serverraum: Keycards und ein Hacking-Modul. **[E]** am Terminal, `Entering Code`-Animation,
vierstelliger Fortschrittsbalken.

Bei 70 % geht der Alarm los. Nicht wegen dir.

> **DURCHSAGE:** „Sicherheitsstufe zwei. Privates Personal, kein Polizeiruf."

*Kein Polizeiruf.* Bagafud ruft nicht die Polizei. Das merkt sich der Spieler.

### Szene 3 — Die erste Schießerei

Private Security, sechs Mann, Gänge. **Erste Waffe: schallgedämpfte Pistole.** Deckung, kurze
Distanzen, wenig Munition.

Fluchtweg: Fenster im dritten Stock, Enterhaken, freier Fall in eine Gasse.

**UI & Gefühl:** Neonfarbene Minimap, rote Sichtkegel. Treffer-Feedback hart und trocken. Der
Soundtrack schneidet beim Fenstersprung ab und lässt nur Wind stehen.

---

## DIE LÜCKE — Akt 2 (neu)

Zwischen Mission 3 und Mission 5 fehlten im Original die Beats, die aus einem Verdacht eine Gewissheit
machen. Drei kurze Missionen, je zehn bis fünfzehn Minuten:

### 3a — „Kleine Summen" *(Nacht)*
Drei Geldautomaten, ein Wettbüro, eine Juwelierkette. Kein Plot, reines Handwerk: das Spiel bringt
dir bei, wie die Nacht arbeitet, bevor es darauf ankommt. Am Ende eine Zeile, die alles trägt:

> **NACHT (Notiz):** *„Nicht für das Geld. Für die Übung."*

### 3b — „Der Zeuge" *(Tag)*
Cabert verhört den Nachtwächter des Sub-Labors. Der Mann beschreibt den Einbrecher: Größe, Gang,
wie er den Kopf hält. Der Spieler erkennt die Beschreibung, bevor Cabert reagiert.

> **WÄCHTER:** „Er stand da wie… entschuldigen Sie. Wie Sie gerade."

Und der Beat aus deiner Notiz, hier platziert:

> **STREIFENPOLIZIST:** „Sie waren doch gestern Nacht schon mal hier."
> **CABERT:** „Nein."

### 3c — „Halvorsens Angebot" *(Tag)*
Der Direktor bietet Cabert die Beförderung an, sofort, mit Versetzung. Er will ihn weg vom Fall.
Freundlich, väterlich, unwiderstehlich — und der Spieler sieht als Einziger, dass es ein Kauf ist.
Keine Action. Nur ein Gespräch und eine Unterschrift, die du verweigern darfst oder nicht. **Beides
führt zum selben nächsten Tag.** Das ist die erste Lüge des Spiels über die eigene Wahlfreiheit — und
die Probe für Mission 8.

---

# MISSION 4 — Schatten im Revier

*Tag. Polizeirevier Nightfall.*

### Der Anlass

Die Nacht braucht die Routen eines Bagafud-Geldtransporters. Die liegen in einem Vorgang, den nur
Halvorsen freigeben kann — und Halvorsen hat Cabert gerade von diesem Fall abgezogen.

**Korrektur zum Original:** Cabert *ist* die Polizei und könnte Routen anfordern. Die Sperre durch
Halvorsen ist der Grund, warum es heimlich sein muss.

### Was du spielst

Stealth ohne Waffe, im vollen Tageslicht, zwischen Kollegen. Kein Alarm — **Verdacht**. Eine Leiste
statt einer Sichtbarkeitsanzeige: Kollegen, die dich zu oft am falschen Ort sehen, füllen sie.

Werkzeuge: Ablenkung (Telefon klingeln lassen), Schlüsselkarte leihen und zurücklegen, ein
Kaffeebecher an der richtigen Stelle.

Am Serverraum: `Entering Code`, dreißig Sekunden. Okonkwo geht zweimal vorbei.

> **OKONKWO:** „Du hast frei."
> **CABERT:** „Ich weiß."
> **OKONKWO:** „Das war keine Frage."

### Der Ausgang

Die Routen sind auf dem Stick. Beim Verlassen zeigt eine Kamera im Flur eine Aufnahme von gestern
Nacht — dieselbe Gestalt, dieselbe Haltung. Halvorsen steht davor und schaut sie an. Er dreht sich
nicht um.

---

# MISSION 5 — Konvoi-Kollaps

*Nacht. Stadtautobahn, gesperrt.*

### Szene 1 — Die Jagd

Der geklaute Sportwagen gegen vier gepanzerte Trucks und zwei Begleitfahrzeuge. Erst fahren, dann
schießen: **EMP-Ladung** auf den Führungswagen, der Konvoi bricht auf.

### Szene 2 — Das Feuergefecht

Auf der gesperrten Autobahn, zwischen brennenden Wracks. **Sturmgewehr.** Militärisches Personal,
kein Security-Dienst mehr. Das ist die Eskalation: Bagafud schickt keine Wachleute, sondern Soldaten.

### Szene 3 — Das Depot

Alles Erbeutete wandert an zwei Orte: die Garage — und **eine Mülltonne neben dem Bagafud-Turm**.
Der Spieler stellt sie selbst dort ab. In Mission 7 holt er sie wieder heraus, und niemand hat es
ihm gesagt.

> **NACHT (Notiz):** *„Das Beste an einer Mülltonne ist, dass niemand hineinsieht, der etwas zu
> verlieren hat."*

---

# MISSION 6 — Die Schlinge zieht sich zu

*Morgen. Caberts Wohnung.*

### Szene 1 — Das Klopfen

Kein Alarm. Ein Klopfen. Dann Okonkwos Stimme durch die Tür:

> **OKONKWO:** „Mach auf. Bitte mach einfach auf."

Du hast dreißig Sekunden, bevor die Tür fällt. In der Zeit musst du zwei Dinge holen: **den USB-Stick**
und **den Plan**. Beide liegen nicht dort, wo du sie zuletzt gesehen hast — die Nacht räumt auf.

### Szene 2 — Die Flucht

SWAT im Treppenhaus. Fenster. Dächer. **Keine Waffe.** Das Spiel lässt dich nicht schießen — nicht
durch eine Sperre, sondern weil Cabert die Waffe nicht zieht, egal was du drückst.

Helikopter, Scharfschützen, Parkour über acht Dächer. Kugeln, denen man ausweicht, indem man in
Bewegung bleibt. Ein Warnsystem im Sinne der Spidey-Sense: kurz vor einem Schuss zuckt der
Bildschirmrand an der Seite, aus der er kommt.

### Szene 3 — Der Sprung

Letztes Dach, keine Anschlussfläche mehr. Unten Sirenen. Der Enterhaken hat noch einen Wurf.

Cabert springt. Schnitt auf schwarz. Zwei Stunden Zeitsprung.

---

# MISSION 7 — THE POINT OF NO RETURN

*Tag. Regen. Bagafud-Turm.*

### Phase 1 — Der Aufstieg

Cabert steht unten am Turm. Verletzt, übermüdet, gesucht. Es regnet in Strömen.

**Kamera von unten steil nach oben.** Wind und Regen brutal laut. Keine Musik.

Enterhaken-Kette an den Fensterscheiben hinauf: **[RMT] zielen → [RMT] greifen**, im Schwung lösen,
sofort neu greifen. Vierzig Stockwerke. Unten heulen die Sirenen und werden leiser, je höher du
kommst — das einzige Mal im Spiel, dass Höhe Sicherheit bedeutet.

### Phase 2 — Das Penthouse-Labor

Durch die Lüftung. Sechs Elite-Wachen. **[F] für lautlose Takedowns** von hinten.

Bei Entdeckung: Alarm, Schotts schließen, Schlüsselkarten müssen von ausgeschalteten Wachen
aufgehoben werden **[E]**. Das Spiel bestraft Entdeckung mit Arbeit, nicht mit Tod.

### Phase 3 — Der Vault

Panzertür. Thermit-Ladung **[E]**. **Fünfundvierzig Sekunden**, in denen die Tür schmilzt und Wellen
von Söldnern kommen, dazu Deckengeschütze mit roten Linsen als Schwachstelle.

Werkzeuge: Sturmgewehr, Rauchgranaten **[4]**, Säulen und Glas, die zerbrechen.

Ist die Tür offen, gehst du langsam hinein. **Die Musik bricht ab. Vollständig.**

---

# MISSION 8 — Der Verrat

*Innerstes Sanctum. Kein Geräusch außer dem Terminal.*

### 1 — Die gefälschte Entscheidung

Zwei Knöpfe auf dem Bildschirm:

> **[ VERNICHTEN ]**  **[ DATEN EXTRAHIEREN ]**

Der Spieler wählt „Vernichten". Klick. **Nichts passiert.** Ein kurzes Bildrauschen.

Der Cursor bewegt sich von allein auf **[ DATEN EXTRAHIEREN ]**.

> **PROMPT:** *Drücke mehrfach [E], um die Kontrolle zu behalten*

Egal wie schnell gedrückt wird: der Balken des Guten bricht ab. Die rote Seite übernimmt ihn ganz.

### 2 — Der mentale Tod

Während der Download läuft, löscht sich das HUD selbst:

- Das Detektiv-Notizbuch bekommt Pixelfehler und verschwindet
- Das Polizeifunk-Icon flackert und geht
- Die Enterhaken-Anzeige bleibt am längsten

> **SYSTEM:**
> `Cabert_Personality_File: CORRUPTED`
> `Deleting…`

Kein 3D-Modell erklärt das. Der Bildschirm erklärt es.

### 3 — Der Umschalter

Die Musik steigert sich — und bricht ab. **Zwei Sekunden Totalstille.**

Dann: FOV schießt hoch, rote Vignette, chromatische Aberration. Der schwere Bass setzt ein.

> **NACHT (über Funk):** „Danke für die Ermittlungsarbeit, Cabert. Ab hier übernehme ich."

### 4 — Epilog

Schwarzbild. Nur eine Tastatur.

Ein Chatfenster öffnet sich. Eine Nachricht geht an Halvorsen:

> *„Ich habe die Waffe. Ab heute gehört die Stadt mir. Wenn du oder deine Leute mich jagen, lösche
> ich einen Distrikt pro Stunde aus. Wir hören voneinander."*

Eine Sekunde auf das Charaktermodell: Hochhausdach, Regen, Tasche mit den Festplatten in der Hand,
Blick hinunter auf die leuchtende Stadt.

**Ergänzung zum Original:** Bevor der Schnitt kommt, ein letztes Bild — **eine Notiz in der
Jackentasche, in Caberts Handschrift, die die Nacht nicht geschrieben hat:**

> *„Sie liest das hier auch."*

Cut to black. Credits.

---

## Was das Drehbuch technisch verlangt

| Bereich | Bauteil | Status |
|---|---|---|
| Szenenablauf | `Mission` + Steps, `MissionSystem` | **steht** |
| Gescriptete Posen | `PlayerAnimation.PlayPose`, Scripted-Layer | **steht** |
| Innenräume | `InteriorDoor`, `Interiors` bei x=5000 | **steht** |
| Blende & Prompt | `ScreenOverlay` | **steht** |
| Karte & Wegpunkte | `MapHUD`, mission-getrieben | **steht** |
| **Untertitel / Dialog** | `CaptionStep` + Untertitelzeile | *für den Prolog* |
| **Mentalisten-Sicht** | Post-Effekt + `Clue`-Komponente | M1 |
| **Tag/Nacht als Missionszustand** | FCG `DayNight` verdrahten | M2 |
| Waffen | Waffenrad, Schusssystem, Deckung | M3 |
| Fahrzeuge | Einsteigen, Fahrphysik, Verfolgung | M2 |
| Verdachtsleiste | Stealth-Wahrnehmung | M4 |
| Spidey-Sense | Randwarnung vor Schüssen | M6 |
| HUD-Zerfall | UI-Elemente einzeln zerstörbar | M8 |

---

*Prämisse, Figuren, Twist und Missionsgerüst: deine. Szenenausbau, Dialog und die Akt-2-Beats: meine.
Drei Korrekturen sind im Text markiert — Handschrift-Match (M1), Halvorsens Sperre (M4),
Epilog-Widerhaken (M8).*
