# Nightfall — Story-Bewertung und Umsetzungsplan

Bezug: `Story roter faden.txt`

---

## 1. Was die Story taugt

**Kurz: sie trägt.** Das ist kein netter Einfall, sondern eine Prämisse, die Gameplay *erzeugt* statt es nur zu rahmen.

Was konkret gut ist:

- **Der Tag/Nacht-Split ist ein Systemdesign, keine Erzählfarbe.** Ermittler am Tag, Dieb in der Nacht — das rechtfertigt zwei komplett verschiedene Mechanik-Sets (Spurensuche/Verhör vs. Stealth/Heist) in *einem* Spiel, ohne dass es beliebig wirkt. Die meisten Indie-Stories geben dir einen Twist; deine gibt dir eine Struktur.
- **Der Twist ist mechanisch, nicht nur narrativ.** Mission 8 — der Button, der nicht reagiert, das QTE, das man nicht gewinnen kann, das HUD, das sich selbst löscht — das ist *ludonarrative* Erzählung. Spec Ops: The Line und Bioshock haben genau damit Geschichte geschrieben. Dass du das ohne ein einziges zusätzliches 3D-Modell erzählst, ist der stärkste Einfall im ganzen Dokument.
- **Die Bio-Waffe ist ein sauberer moralischer Motor.** Sie zwingt Cabert, auf der Seite des Diebs zu stehen, bevor er weiß, dass er der Dieb ist. Das Publikum ist mitschuldig, bevor es das merkt.
- **Der Aufhänger sitzt.** „Sie waren doch gestern Nacht schon mal hier" / „Nein" — ein Satz, der die ganze Story vorwegnimmt und beim zweiten Durchspielen anders klingt. Genau so schreibt man einen Cold Open.

Wo ich kritisch bin:

- **Der Twist ist zu früh sichtbar.** Der Spieler ahnt „ich bin der Dieb" spätestens in Mission 2, weil er die Nacht-Persönlichkeit *selbst spielt*. Die Handschriftanalyse in Mission 1 sagt es ihm sogar direkt. Das ist nicht schlimm — dramatische Ironie funktioniert — aber dann darf die Story nicht so tun, als wäre das die Überraschung. **Der echte Twist muss Mission 8 sein:** nicht *dass* du der Dieb bist, sondern *dass die böse Seite gewinnt*. Mission 1 sollte deshalb weniger deutlich sein: kein „Handschrift-Match: 99.8 % (Cabert)", sondern „Handschrift-Match: 99.8 % — Vergleichsprobe nicht in der Datenbank". Der Spieler zieht den Schluss selbst.
- **Akt 2 ist eine Lücke.** Zwischen Mission 1 und Mission 7 steht „kleinere Budget-Raube und Datenklau". Das sind 4 von 8 Missionen, die im Dokument nur eine Zeile haben. Da entscheidet sich, ob das Spiel 3 oder 12 Stunden lang ist.
- **Mission 4 hat ein Logikproblem.** Cabert hackt Server im eigenen Revier, um Transporter-Routen abzugreifen — aber er *ist* die Polizei. Er könnte die Routen anfordern. Es braucht einen Grund, warum er es heimlich tun muss (z. B. die Routen liegen in einem Vorgang, auf den nur der korrupte Chef Zugriff hat).
- **Der Epilog braucht einen Widerhaken.** „Ab heute gehört die Stadt mir" ist ein starker Schlusssatz, aber der Spieler hat gerade verloren und bekommt nichts zurück. Ein letztes Bild, das andeutet, dass Cabert nicht ganz weg ist — ein Notizzettel in seiner eigenen Handschrift, den die Nacht-Seite nicht geschrieben hat — macht aus einem Downer-Ende einen Cliffhanger.

---

## 2. Wie sie in das gebaute Spiel passt

Das Fundament steht bereits erstaunlich passgenau:

| Story braucht | Steht schon im Projekt |
|---|---|
| Dächer-Parkour, Grapple-Verfolgung (M1, M6, M7) | `GrappleSystem`, `GlideSystem`, `GrappleAnchors` |
| Autojagd (M2, M5) | FCG-Verkehrssystem, `SportCar`, `PickupTruck` |
| Polizeirevier, Bagafud-Tower, dein Apartment | 18 gesetzte `MapPoint`-Standorte, u. a. Polizei Hauptwache, Revier Süd, Dein Apartment |
| Minimap mit Sichtkegeln (M3) | `MapHUD` mit Marker-System — Sichtkegel sind ein Marker-Typ mehr |
| Schießerei (M3, M5, M7) | Nokobot M1911 mit Animationen, HK416-Modell |
| Stadt bei Tag und Nacht | FCG `DayNight` (`isNight`, `isStreetLights`) — noch nicht verdrahtet |

**Was die Story vom Weltbau zusätzlich verlangt:**

1. **Bagafud-Tower.** Braucht ein eigenes, wiedererkennbares Hochhaus. Kandidat steht schon: `BC-083` bei (18, 82) — 91 m hoch, das höchste Gebäude der Stadt. Das wird der Turm.
2. **Innenräume.** Erst vier: Apartment, Revier, Sub-Labor, Penthouse/Vault. Alles andere kann geschlossen bleiben.
3. **Tag/Nacht als Missionszustand**, nicht als Zyklus. Jede Mission setzt fest, ob Tag oder Nacht — sonst kollidiert die freie Uhr mit der Erzählung.
4. **Mentalisten-Sicht [V]** — Entsättigung + gelbe Umrandung. Das ist ein Post-Processing-Effekt plus ein `Clue`-Komponententyp, kein großes System.

---

## 3. Was ich von dir brauche

Nach Priorität. Alles mit ⬜ blockiert mich aktuell nicht, alles mit 🟥 schon.

### 🟥 Blockiert mich jetzt

**A. Animationen.** Ich kann keine Assets von Mixamo oder dem Asset Store ziehen — beides verlangt einen eingeloggten Account. Ich brauche von dir als `.fbx` (Humanoid-Rig, dann retargete ich selbst):

| Zweck | Was genau | Wo |
|---|---|---|
| Pistole halten/zielen/nachladen | Kommt mit Nokobot mit — ✅ schon da |
| Gewehr halten/zielen/nachladen | fehlt für die HK416 | Mixamo: „Rifle Idle", „Rifle Aiming Idle", „Reloading" |
| Stealth-Takedown von hinten | 1 Animation | Mixamo: „Sword And Shield Kick"/„Standing Melee" oder Suche „Takedown" |
| Klettern/Ledge-Grab | 2 Animationen | Mixamo: „Hanging Idle", „Climbing Up Wall" |
| Schwimmen (falls doch gewünscht) | 2 Animationen | Mixamo: „Swimming", „Treading Water" |
| Auto einsteigen/aussteigen | 2 Animationen | Mixamo: „Entering Car" |

Mixamo ist kostenlos, du lädst als **FBX for Unity, ohne Skin** herunter und legst sie in `Assets/Nightfall/Art/Animations/`. Sag mir Bescheid, wenn sie drin liegen — ich baue den Animator.

**B. Eine Entscheidung zum Umfang von Akt 2.** Soll ich die vier fehlenden Missionen entwerfen, oder schreibst du sie? Ich kann einen Vorschlag liefern, aber das ist deine Story.

### ⬜ Brauche ich später

- **Musik/Sound.** Der Twist in Mission 8 lebt zu 50 % vom Audio (Stille, dann Bass). Ohne Ton ist es nur ein Bildschirm. Kostenlos brauchbar: Kevin MacLeod, Pixabay Music, freesound.org für SFX.
- **Stimme für den Monolog der Nacht-Persönlichkeit** (ein Satz). Kann auch Text-Overlay bleiben.
- **Ein Gesicht für Cabert.** Aktuell läuft ein generisches Modell. Wenn du einen bestimmten Look willst, sag es; sonst nehme ich einen aus deinen Character-Packs.

### Was ich selbst mache, ohne dich

- Innenräume für die vier Story-Gebäude
- Mentalisten-Sicht, Clue-System, Spurentrail
- Tag/Nacht-Verdrahtung an FCGs `DayNight`
- Waffenrad, Schusssystem, Deckung
- Missionsablauf-System (Trigger, Ziele, Cutscene-Kamerafahrten)

---

## 4. Vorschlag: Reihenfolge

1. **Prolog + Mission 1 komplett spielbar** — das beweist die Schleife (Mentalisten-Sicht, Dächer, Grapple, Cutscene, Schlafen). Wenn das trägt, trägt das Spiel.
2. Waffen + Mission 3 (erste Schießerei)
3. Fahrzeug-Handling + Mission 2
4. Rest von Akt 1, dann Akt 2 füllen
5. Mission 7/8 zuletzt — das ist die teuerste und sollte auf fertigen Systemen aufsetzen

---

*Erstellt aus `Story roter faden.txt`. Das Weltbau-Fundament (Stadt, Insel, Fluss, Karte, Standorte) steht bereits.*
