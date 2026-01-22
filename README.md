# RIFT COMMAND: The Lost Citadel

![Status](https://img.shields.io/badge/Status-Concept%20Phase-blue)
![Engine](https://img.shields.io/badge/Engine-Godot%20)
![Genre](https://img.shields.io/badge/Genre-Roguelite%20Sim-red)

> **High Concept:** Ein Roguelite-Management-Sim, in dem du eine uralte Alien-Stadt verwaltest und Expeditions-Teams durch ein Dimensionstor ("The Aperture") schickst.

> **Elevator Pitch:** *XCOM* trifft auf *Darkest Dungeon* mit dem Ressourcen-Management von *Frostpunk* – präsentiert mit 90s-Style FMV-Cutscenes.

---

## 📑 Inhaltsverzeichnis
1. [Übersicht & Vision](#1-übersicht--vision)
2. [Core Gameplay Loop](#2-core-gameplay-loop)
3. [Die Zitadelle (Base Building)](#3-die-zitadelle-base-building)
4. [Das Universum (Welt-Generierung)](#4-das-universum-welt-generierung)
5. [Personal & Dispatch Management](#5-personal--dispatch-management)
6. [Sieg- & Niederlage-Bedingungen](#6-sieg--niederlage-bedingungen)
7. [Technische Umsetzung & Assets](#7-technische-umsetzung--assets)
8. [Development Roadmap](#8-development-roadmap)

---

## 1. Übersicht & Vision

Du spielst den Commander der **"Terran Vanguard"**, gestrandet in einer verlassenen Stadt ("Die Zitadelle") einer ausgestorbenen Hochkultur. Deine einzige Verbindung zum Universum ist die **Aperture** – ein Tor, das Wurmlöcher zu fernen Welten öffnet.

### USP (Unique Selling Points)
* **Indirekte Kontrolle:** Du kämpfst nicht selbst. Du stellst Teams zusammen, rüstest sie aus und triffst taktische Entscheidungen per Funk.
* **FMV Storytelling:** Briefings und Events werden durch "Greenscreen"-Videoaufnahmen (Trash/Retro Charme) erzählt.
* **3-Trait Planet System:** Prozedurale Welten basierend auf logischer Kombinatorik.

---

## 2. Core Gameplay Loop

1.  **Basis-Phase (Die Zitadelle):** Ressourcen verwalten, Gebäude reparieren, Forschung, Crew-Therapie.
2.  **Dispatch-Phase (The Aperture):** Ziel wählen, Team zusammenstellen, Ausrüstung kaufen.
3.  **Missions-Phase:** Das Team reist. Text-Events und rundenbasierte Taktik-Entscheidungen (Auto-Battler mit Eingriffsmöglichkeiten).
4.  **Resultat:** Beute (Tech/Ressourcen) oder Verluste (Tod/Verletzung).
5.  **Progression:** Die Stadt wächst, Bedrohung steigt.

---

## 3. Die Zitadelle (Base Building)

Das Herz des Spiels. Isometrische oder Querschnitts-Ansicht der Stadt. Anfangs ist alles dunkel und versiegelt.

### Wichtige Sektoren (Upgradbar)
* **Aperture Command (Start):** Bestimmt Reichweite und Stabilität des Tors.
    * *Upgrade:* Schnelleres Anwählen (Flucht), Filterung von Strahlung.
* **Bio-Dome:** Produziert Nahrung und Sauerstoff.
* **Die Gießerei (Foundry):** Verarbeitet Rohstoffe in Baumaterial und Waffen.
* **Neuro-Klinik:** Heilt physische Wunden und "Weltraum-Wahnsinn" (Stress).
* **Diplomatische Suite:** Ermöglicht Verhandlungen mit Alien-Botschaftern.
* **Das Archiv:** Generiert Forschungspunkte (Intel).
* **Klon-Kammer (Late Game):** Teure Wiederbelebung von Unique Heroes (kostet enorme Energie + "Seelen-Fragmente").
* **Hangar Bay:** Späterer Bau von kleinen Shuttles (für Space-Missionen) und Frachtern.

---

## 4. Das Universum (Welt-Generierung)

Kein Planet ist gleich. Jeder Zielort wird aus 3 Komponenten (Traits) generiert, die Wahrscheinlichkeiten für Events und Schwierigkeit bestimmen.

### Das 3-Trait-System
`[BIOM] + [STATUS] + [BEWOHNER]`

#### A. Biom (Die Umgebung)
* **Arid (Wüste):** Hoher Energieverbrauch für Lebenserhaltung.
* **Toxic (Gift):** Benötigt Schutzanzüge. Ohne Schutz: Krankheit alle 3 Runden.
* **Ruins (Tech):** Hohe Chance auf Artefakte, geringe Chance auf Nahrung.
* **Verdant (Dschungel):** Viel Nahrung, viele wilde Tiere (Kampf).

#### B. Status (Der aktuelle Zustand)
* **Dormant (Ruhig):** Geringe Event-Dichte. Sicher zum Abbauen.
* **War-Torn (Kriegsgebiet):** Doppelte Kampfchance. Hohe Beute (Waffen).
* **Unstable (Instabil):** Zeitlimit! Planet kollabiert in X Runden.
* **Quarantined (Seuche):** Chance, dass Team infiziert zurückkehrt (Gefahr für Basis!).

#### C. Bewohner (Die dominante Kraft)
* **None:** Nur wilde Fauna oder Automaten.
* **The Synod:** Religiöse Fanatiker (Stark, Tech-basiert).
* **Iron Pact:** Industrielle Plünderer (Viele, ballistische Waffen).
* **The Void-Weavers:** Mysteriöse Psioniker (Selten, gefährlich, diplomatisch möglich).

> **Beispiel-Generierung:**
> * **Ziel:** PX-99
> * **Traits:** `[Ruins]` + `[Unstable]` + `[Iron Pact]`
> * **Analyse:** "Wir müssen schnell rein, antike Tech bergen, bevor der Planet explodiert, und dabei Plünderer abwehren."

---

## 5. Personal & Dispatch Management

### Crew Klassen
* **Vanguard (Soldat):** Kampfbonus, kann schwere Rüstung tragen.
* **Scholar (Wissenschaftler):** Bonus auf Tech-Events, hackt Terminals.
* **Diplomat:** Schaltet "Verhandeln" frei, handelt bessere Preise aus.
* **Engineer:** Repariert Ausrüstung im Feld, baut Barrikaden.

### Unique Heroes (Die "Stars")
Besondere Charaktere mit eigener Backstory und fixen Traits.
Beispieltraits:
* **Xeno-Hasser:** Weigert sich, Aliens im Team zu heilen.
* **Alte Garde:** Immun gegen Panik.
* **Jinx:** 5% Chance, dass Tech im Umkreis ausfällt (Bad Luck), aber +20% Crit Chance.

### Das Dispatch-Interface
Du siehst nicht das direkte Gefecht in 3D, sondern taktische Daten (Balken für Team-Gesundheit, Stress, Munition).

**Entscheidungs-Loop Beispiel:**
1.  *Alert:* "Feindkontakt: Patrouille der Synod."
2.  **[Option A - Vanguard]:** Hinterhalt legen (Erfolg: 70%).
3.  **[Option B - Diplomat]:** Bestechung anbieten (Kosten: 50 Gold).
4.  **[Option C]:** Rückzug zum Tor!

Die Erfolgschancen hängen von den Stats des Einsatzteams ab. Wenn man im Briefing gut wählt, dann hat man höhere Chancen. Aber für manche Missionen hat man evtl. nicht die richtigen Leute, weil noch zu "schwach".

---

## 6. Sieg- & Niederlage-Bedingungen

### Game Over (Lose States)
Das Spiel endet, wenn einer der folgenden Zustände eintritt:
* **Critical Power Failure:** Energie fällt auf 0 und bleibt dort für 3 Tage (Lebenserhaltung versagt).
* **Command Decapitation:** Die Moral in der Basis fällt auf 0 -> Meuterei, du wirst abgesetzt.
* **Invasion:** Die Verteidigungswerte der Zitadelle fallen auf 0 während eines Angriffs -> Basis überrannt.
* **Isolation:** Das Aperture-Tor wird irreparabel zerstört (durch Sabotage oder Fehlfunktion).

### Sieg-Bedingungen (Wählbar pro Run)
* **Dominion:** Besiege die Hauptflotten der drei rivalisierenden Fraktionen.
* **Ascension:** Schalte den gesamten Tech-Tree der Zitadelle frei und aktiviere die "Master Engine".
* **Coalition:** Erreiche den Ruf "Verbündet" mit allen Fraktionen (Diplomatie-Sieg).

---

## 7. Technische Umsetzung & Assets

* **Engine:** Godot
* **Grafikstil:** Pixel Art oder stilisierte 2D Vector Art für die UI/Basis.

### FMV (Full Motion Video)
Realfilm-Sequenzen für Briefings.
* **Stil:** "Command & Conquer" Vibes.
* **Setup:** Commander vor Greenscreen, statisches Rauschen, Scanlines drüberlegen.
* **Schauspieler:** Du selbst, Freunde, oder Freelancer (Low Budget Charme ist gewollt!).

### Meta Progression
Nach jedem Run erhältst du "Memory Fragments".
* **Freischaltbar:** Neue Start-Völker (Durch Diplamatie Freischaltbar), neue Unique Heroes im Pool, permanente Blueprints.

---

## 8. Development Roadmap (Solo Dev Scope)

* **Phase 1 (Prototype):** Nur Text & UI. Basis-Bau, Ressourcen-Tick, einfache Missionen (Würfelglück).
* **Phase 2 (Content):** Implementierung des 3-Trait-Systems und der ersten 2 Fraktionen.
* **Phase 3 (Visuals):** Pixel Art für die Stadt, Aufnahme der ersten FMV Clips (Intro/Outro).
* **Phase 4 (Polish):** Balancing, Unique Items, Events, Musik.

---

> **Dev Note:** Der Fokus liegt auf "Decision Making". Gute Grafik ist nett, aber die Spannung, ob das Lieblingsteam rechtzeitig durch das Tor zurückkommt, bevor die Iris (das Schild) schließt, ist das Kern-Erlebnis.
