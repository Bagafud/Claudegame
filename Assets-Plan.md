# Nightfall — was da ist, was fehlt, was es kostet

Neu geschrieben am 13.09.2026, nachdem die erste Fassung dir Sachen empfohlen hat, die du schon
besitzt. **Ab hier nur noch: was im Projekt liegt, und wenn etwas fehlt, kostenlos.**

---

## 1. Was du hast und was ich nicht gesehen hatte

| Pack | Wofür | Stand |
|---|---|---|
| **Realistic Car Controller Pro** | Mission 2 und 5, komplett | war schon drin, ich hatte dir einen Controller empfohlen |
| **Dorschizo / Free Military Vehicles** | Militär-LKW, Mission 5 Konvoi | drin |
| **Sci-fi** (models/scenes) | modulare Böden, Decken, Konsolen, Lampen, Fässer → **Labor für Mission 3 und 7** | drin, kostenlos |
| **Residential Buildings Set** | 10 Wohnhäuser für die Stadt | drin |
| **Invector 3rd Person LITE** | Locomotion-Referenz | drin |
| **Footsteps – Essentials** | 12 Untergründe, 464 Clips | **jetzt verdrahtet** |

### Die Animationen, die es angeblich nicht gab

Ich hatte dir Mixamo-Downloads aufgeschrieben. Alle vier liegen schon da, nur anders benannt:

| Was ich „fehlt" nannte | Was tatsächlich da ist |
|---|---|
| Stealth-Takedown von hinten | `Double Dagger Stab` |
| In Deckung gehen | Fantacode TPC: kompletter Crouch-Satz (idle, walk, back, left, right) |
| Über Hindernis springen | `Jump Down`, `Dive and Roll`, `Entrywindowfromstanding`, `Sprint To Wall Climb` |
| Treffer-Reaktionen | `Being Electrocuted`, `Dying`, `Dodging Right` |

Ich habe nach dem Namen gesucht, den *ich* vergeben hätte, statt nach der Fähigkeit. Steht jetzt in
meinem Gedächtnis, damit es nicht nochmal passiert.

---

## 2. Was wirklich fehlt — und die kostenlose Antwort darauf

### Mission 4, Polizeirevier
Die ehrliche Antwort ist **nicht kaufen**. Ein Revier ist Flure, Großraumbüro, Serverraum,
Verhörzimmer — und genau dafür habe ich gerade den Wandbauer geschrieben, der das Dachversteck
gebaut hat: Öffnungen werden in Metern angesagt, die Wand wird drumherum gebaut, Türen und Fenster
stimmen per Konstruktion. Mit dem Apartment Kit (hast du) plus dem Sci-fi-Pack (hast du) baue ich
das Revier in Unity, so wie die Hütte.

Zum Ausstatten, falls du magst, alles kostenlos:
- [Office Pack – Free](https://assetstore.unity.com/packages/3d/props/interior/office-pack-free-258600)
- [Old Office Props Free](https://assetstore.unity.com/packages/3d/props/interior/old-office-props-free-53735)
- [Free Sci-Fi Office Pack](https://assetstore.unity.com/packages/3d/environments/sci-fi/free-sci-fi-office-pack-195067) — bringt Server und Rechner mit

### Dach-Props
Gestrichen. Du hast gesagt, die Dächer passen, und du hast recht: das Problem waren nie die Props,
sondern dass die halbe Stadt keine Ankerpunkte hatte. Das ist gelöst.

### Muzzle-Flash
Du hast Impact gefunden, Muzzle nicht. Das ist kein Kauf — ein Mündungsfeuer ist ein Quad mit
additivem Material, zwei Frames lang. Schreibe ich, wenn wir bei Mission 3 sind.

### Der Rest
| Mission | Fehlt | kostenlos lösbar? |
|---|---|---|
| 2 Autojagd | Sirene, Bremsspuren | RCC Pro bringt Skid und Impact mit; Sirene von freesound.org |
| 3 Labor | Wachen | `Gang members` + `Police_officer` umskinnen |
| 5 Konvoi | Explosion, EMP | Unity VFX Graph, selbst gebaut |
| 6 SWAT | SWAT-Modelle | `Police_officer` in dunkel + Weste aus `npc_casual_set` |
| 7 Heist | Tresortür, Turrets | in Unity modelliert, wie die Hütte |
| 8 Finale | **nichts** | braucht Musik und eine Stimme, kein Modell |

Musik: Kevin MacLeod, Pixabay Music. SFX: freesound.org. Beides kostenlos und für einen Prototyp
mehr als gut genug.

---

## 3. Was diese Runde geändert wurde

- **Enterhaken-Anker**: 10.172 → **17.069**, Kartenrand vorher 0 %, jetzt vollständig. Namenserkennung
  raus, Rasterabtastung über die ganze Karte rein. 807 ms.
- **Dachhütte**: neu gebaut mit echten Öffnungen. Tür ist eine Tür, Fenster ist ein Fenster.
  Teleport abgeschaltet.
- **Schritte**: 464 Clips, 12 Untergründe, Material-Erkennung. Dächer klingen nach Kies, die Wohnung
  nach Fliese, die Straße nach Stein.
- **Dialoge**: alles neu. Fünf Figuren, fünf Stimmen, richtige Umlaute.
