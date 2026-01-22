# RIFT COMMAND: The Lost Citadel

![Status](https://img.shields.io/badge/Status-Concept%20(TBA)-lightgrey)
![Engine](https://img.shields.io/badge/Engine-Godot%204.x-blue)
![Genre](https://img.shields.io/badge/Genre-Roguelite%20Sim-red)

> **High Concept:** Ein Roguelite-Management-Sim, in dem du eine uralte Alien-Stadt verwaltest und Expeditions-Teams durch ein Dimensionstor ("The Aperture") schickst.

> **Elevator Pitch:** *FTL* trifft auf *XCOM* mit dem Ressourcen-Management von *Frostpunk* – präsentiert mit 90s-Style FMV-Cutscenes.

---

## 📑 Inhaltsverzeichnis
1. [Übersicht & Vision](#1-übersicht--vision)
2. [Core Gameplay Loop](#2-core-gameplay-loop)
3. [Die Zitadelle (Base Management)](#3-die-zitadelle-base-management)
4. [Das Universum (Welt-Generierung)](#4-das-universum-welt-generierung)
5. [Personal & Dispatch Management](#5-personal--dispatch-management)
6. [Sieg- & Niederlage-Bedingungen](#6-sieg--niederlage-bedingungen)
7. [Technische Umsetzung & Assets](#7-technische-umsetzung--assets)
8. [Development Roadmap](#8-development-roadmap)

---

## 1. Übersicht & Vision

Du spielst den Commander der **"Terran Vanguard"**, gestrandet in einer verlassenen Stadt ("Die Zitadelle") einer ausgestorbenen Hochkultur. Deine einzige Verbindung zum Universum ist die **Aperture** – ein Tor, das Wurmlöcher zu fernen Welten öffnet.

### USP (Unique Selling Points)
* **FTL-Style Base View:** Top-Down Ansicht der Stadt mit Raum-Management (Türen, Sauerstoff, Energie).
* **Indirekte Kontrolle (Dispatch):** Missionen laufen halb-automatisch, du greifst nur bei kritischen Taktik-Entscheidungen ein.
* **FMV Storytelling:** Briefings und Events werden durch "Greenscreen"-Videoaufnahmen (Trash/Retro Charme) erzählt.
* **3-Trait Planet System:** Prozedurale Welten basierend auf logischer Kombinatorik.

---

## 2. Core Gameplay Loop

1.  **Basis-Phase (Die Zitadelle):** Energie verteilen, Räume abriegeln, Gebäude reparieren, Forschung.
2.  **Dispatch-Phase (The Aperture):** Ziel wählen, Team zusammenstellen, Ausrüstung kaufen.
3.  **Missions-Phase:** Das Team reist. Text-Events und Taktik-Entscheidungen (Auto-Battler mit Eingriffsmöglichkeiten).
4.  **Resultat:** Beute (Tech/Ressourcen) oder Verluste (Tod/Verletzung).
5.  **Progression:** Die Stadt wächst, Bedrohung steigt, neue Völker werden freigeschaltet.

---

## 3. Die Zitadelle (Base Management)

Das Herz des Spiels. **Top-Down Ansicht** (wie FTL Blueprint Mode). Du kontrollierst nicht die Figuren direkt, sondern die Systeme der Stadt.

### FTL-inspirierte Mechaniken
* **Door Control System:** Öffne und schließe Schotts strategisch.
    * *Defense:* Wenn Aliens in die Basis eindringen (Gate-Durchbruch), verriegele Sektoren, um sie aufzuhalten.
    * *Hazard:* Wenn ein Feuer ausbricht oder ein biologischer Unfall passiert, entziehe dem Raum den Sauerstoff ("Venting").
* **Power Grid:** Die Stadt hat begrenzte Energie.
    * *Taktik:* Willst du das Tor anwählen, musst du Energie von der Lebenserhaltung oder den Schilden abziehen.
* **Überwachung:** Sensoren zeigen Feindbewegungen in der Stadt an. Upgrades erlauben automatische Abwehrmaßnahmen (Auto-Turrets in Gängen).

### Wichtige Sektoren (Ausbau & Crew-Stationierung)
* **Aperture Command:** Tor-Steuerung. Besatzung hier erhöht die Anwahl-Geschwindigkeit (Flucht).
* **Bio-Dome:** Produziert Nahrung/O2.
* **Die Gießerei (Foundry):** Crafting von Waffen/Material.
* **Neuro-Klinik:** Heilt Wunden und Stress.
* **Hangar Bay:** Späterer Bau von kleinen Shuttles (Puddle Jumpers) für Space-Missionen.

---

## 4. Das Universum (Welt-Generierung)

Kein Planet ist gleich. Jeder Zielort wird aus 3 Komponenten (Traits) generiert.

### Das 3-Trait-System
`[BIOM] + [STATUS] + [BEWOHNER]`

#### A. Biom (Die Umgebung)
* **Arid:** Hoher Energieverbrauch.
* **Toxic:** Benötigt Schutzanzüge. Ohne Schutz: Krankheit.
* **Ruins:** Tech-Loot hoch, Nahrung niedrig.
* **Verdant:** Nahrung hoch, wilde Tiere (Kampf).

#### B. Status (Situation)
* **Dormant:** Sicher zum Abbauen.
* **War-Torn:** Kampfchance x2, Waffen-Loot.
* **Unstable:** Zeitlimit (Planet kollabiert).
* **Quarantined:** Infektionsgefahr für Crew.

#### C. Bewohner (Fraktion)
* **None:** Nur Fauna/Automaten.
* **The Synod:** Religiöse Fanatiker (Tech/Energy).
* **Iron Pact:** Industrielle Plünderer (Ballistik).
* **The Void-Weavers:** Psioniker (Diplomatie möglich).

---

## 5. Personal & Dispatch Management

### Crew Klassen
* **Vanguard (Soldat):** Kampfbonus, schwere Rüstung. Wichtig für Verteidigung.
* **Scholar (Wissenschaftler):** Hackt Terminals, Bonus auf Forschung in der Basis.
* **Diplomat:** Schaltet Handlungsoptionen frei.
* **Engineer:** Repariert Ausrüstung und Basis-Systeme.

### Unique Heroes ("Stars")
Besondere Charaktere mit Backstory und *fixen* Traits.
* **Xeno-Hasser:** Heilt keine Aliens.
* **Alte Garde:** Immun gegen Panik.
* **Jinx:** Bad Luck Aura (Tech fällt aus), aber hohe Crit-Chance.

### Das Dispatch-Interface
Kein 3D-Kampf, sondern taktisches UI (Gesundheit, Stress, Munition).

**Entscheidungs-Loop:**
1.  *Alert:* "Feindkontakt: Patrouille der Synod."
2.  **[Option A - Vanguard]:** Hinterhalt (70% Erfolg).
3.  **[Option B - Diplomat]:** Bestechung (Kosten: 50 Gold).
4.  **[Option C]:** Rückzug!

> *Note:* Erfolg hängt von Crew-Stats und Vorbereitung (Briefing) ab.

---

## 6. Sieg- & Niederlage-Bedingungen

### Game Over (Lose States)
* **Critical Power Failure:** 3 Tage ohne Energie (Lebenserhaltung versagt).
* **Mutiny:** Moral fällt auf 0.
* **Overrun:** Basis-Verteidigungswert fällt auf 0 während Invasion.
* **Isolation:** Tor zerstört.

### Sieg-Bedingungen (Wählbar pro Run)
* **Dominion:** Alle Feindflotten besiegen.
* **Ascension:** Master Engine aktivieren (Tech-Sieg).
* **Coalition:** Alle Fraktionen verbünden (Diplomatie-Sieg).

---

## 7. Technische Umsetzung & Assets

* **Engine:** Godot 4.x
* **Grafikstil:**
    * **Basis:** Top-Down Pixel Art (Blueprint Look).
    * **UI:** Retro-Futuristisch (CRT Monitor Style).
* **FMV (Full Motion Video):** Realfilm-Briefings vor Greenscreen (C&C Style).
* **Meta Progression:** "Memory Fragments" schalten neue Start-Völker, Helden und Blueprints frei.

---

## 8. Development Roadmap (Solo Dev Scope)

* **Start:** TBA (Nach Abschluss des aktuellen Projekts).
* **Phase 1 (Prototype):** Top-Down Basis Bewegung, Türen-Mechanik, Ressourcen-Tick.
* **Phase 2 (Systems):** Dispatch-Logik, Event-System, Welt-Generierung.
* **Phase 3 (Content & Art):** Pixel Art Sets, FMV Aufnahme Intro.
* **Phase 4 (Polish):** Balancing, Musik, UI Juice.

---

> **Dev Note:** Der Fokus liegt auf "Crisis Management". Das Gefühl, Türen zu verriegeln, während man verzweifelt versucht, das Tor anzuwählen, um das Team nach Hause zu holen, ist der Kern des Spiels.
