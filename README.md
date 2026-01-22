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

Das ganze ist Rundenbasiert, also die Phasen, aber innerhalb der einzelnden Phasen bewegen sich die Einheiten durch die Stadt wirkt Lebendiger. 
Um einen Run zu starten wählt man ein Volk und dann eine Startbesatzung.

Je nach Meta Progression kann man 1-N Uniques direkt zum Start mitnehmen, aber der Commandant ist immer ein Unque, also wähle mit bedacht. 
Wie viele restlichen Einheiten mitgehen wird durch den Schwierigkeitsgrad bestimmt den man wählt, aber zuerst 3 Forscher und 4 Soldaten und halt der eine Unqiue. 

Neue Manchaftsmitglieder kann man durch Zufallsereignisse durch MIssionen erhalten oder halt durch Nachschubsanfoderungen. 
Wie schnell hängt von der Ausbaustufe der Basis ab. Zuerst alle 5 Runden kann man bestellen, und nach weiteren 5 Runden bekommt man es dann, und kann dann erneut bestellen, was wieder 5 Runden dauert. Naja doer so ähnlich. 
Die Menge an bestellten Ressourcen hängt von dem ab wie Erfolgreich man Missionen oder Forschungen bewältigt. Für alles bekommt man Credits von dem Heimatplaten die man dann tauschen kann.
Manchmal kann man aber auch mit anderen Völkern handeln, zuerst teurer als Heimatplaten, aber wenn Beziehung gut ist oder sie Angst haben  vor euch, dann kann man den Preis auch drücken. 

Kaufne kann man:
- Neue Besatzung auch manchmal mit Glück Uniques
- Ressourcen wie Nahrung oder Zusatzgeneratoren
- Waffen der Heimatfraktion
- etc.

1.  **Basis-Phase (Die Zitadelle):** Energie verteilen, Räume abriegeln, Gebäude reparieren, Forschung, Dinge herstellen wie z.B. Waffen, Leute befördern..
2.  **Dispatch-Phase (The Aperture):** Ziel wählen, Team zusammenstellen, Ausrüstung wählen.
3.  **Missions-Phase:** Das Team reist. Text-Events und Taktik-Entscheidungen (Auto-Battler mit Eingriffsmöglichkeiten bzw. Eintscheidungen).
4.  **Basis-Ereignis:** Manchmal ereilt die Basis ein Zufallserigniss während die Mission gerade läuft. Angriffe, man wird angewählt von einem Händler, Diplomatie Besuch (könnte + geben in Diplomatie könnte aber auch ein Spy Versuch oder Sabotage sein), Unwetter, Parasiet, Brand, etc. -> Hier eine Art Karma Sytem nicht zu viele schlimme Dinge oder 2 Superschlimme Dinge dürfen hintereinaner passieren. Generell sollte diese Phase nicht jedes mal passieren. Eher seltener, aber dafür umso bedeutener für den Run. So fühlt sich jeder Run wie eine Staffel deiner Lieblings Scifi Serie an.
5.  **Resultat:** Beute (Tech/Ressourcen) oder Verluste (Tod/Verletzung).
6.  **Progression:** Die Stadt wächst, Bedrohung steigt, neue Völker werden freigeschaltet.

---

## 3. Die Zitadelle (Base Management)

Das Herz des Spiels. **Top-Down Ansicht** (wie FTL Blueprint Mode). Du kontrollierst nicht die Figuren direkt, sondern die Systeme der Stadt. Figuren bewegen sich aber durch die Stadt. Sind sie verletzt gehen sie eher in die Krankenstation (obwohl sie alle in der Base mit der Zeit heilt), manchmal in ihre Kabine oder essen was. Teils abhängig von den Werten und teils einfach RND. 

### FTL-inspirierte Mechaniken
* **Door Control System:** Öffne und schließe Schotts strategisch.
    * *Defense:* Wenn Aliens in die Basis eindringen (Gate-Durchbruch), verriegele Sektoren, um sie aufzuhalten.
    * *Hazard:* Wenn ein Feuer ausbricht oder ein biologischer Unfall passiert, entziehe dem Raum den Sauerstoff ("Venting"). Manchmal muss man so Besatzung evtl. Opfern.
* **Power Grid:** Die Stadt hat begrenzte Energie.
    * *Taktik:* Willst du das Tor anwählen, musst du Energie von der Lebenserhaltung oder den Schilden abziehen.
* **Überwachung:** Sensoren zeigen Feindbewegungen in der Stadt an. Upgrades erlauben automatische Abwehrmaßnahmen (Auto-Turrets in Gängen).

### Wichtige Sektoren (Ausbau & Crew-Stationierung)
* **Aperture Command:** Tor-Steuerung. Besatzung hier erhöht die Anwahl-Geschwindigkeit (Flucht).
* **Bio-Dome:** Produziert Nahrung/O2.
* **Die Gießerei (Foundry):** Crafting von Waffen/Material.
* **Neuro-Klinik:** Heilt Wunden und Stress.
* **Hangar Bay:** Späterer Bau von kleinen Shuttles (Puddle Jumpers) für Space-Missionen.
* **Defense Tower:** Verteidigt den Planeten. Defensive Anlagen, Schutzschild, Tarnschild etc.
* **Ancient Libary:** Ist eine Bibliothek die massiv Energie verbraucht aber alte Tech enthält, erfodert neben Energie auch riesiegen zeitlichen Übersetzungsaufwand. Manchmal sind Informationen auch nicht ganz voll weil Datensatz beschädigt (Minigame?)
* **Command Room:** Enhätl Sensoren wie Lebenszeichendetekdotren, Energieanzeige, Türsteuerung. Auf höchster Stufe auch Triebwerke für die Stadt, aber diese benötigen zusätzlich maximale Energie und Schildausbau
* **Gym:** Offensive und Defensive Stats werden verbessert
* **Holo-Deck:** Macht Chars ausgeglichender, und Glücklicher -> Erhöt Diplomatie
* **Clone-Lab:** Teuer, aber Backups von Unique Chars möglich. Zuchtprogramm mit Qnique Traits
* **Generator Room:** Erst Notstromgeneratoren bis hin zu Nullpunktenergie
* **Quartiere:** Zufriedenheit/Moral+, Stat Booster,
* **Messe:** XP Buff

* *Hinweis:* Nicht alle Räume haben alle Funktionen direkt, oder die Funktionerne werden mit steigender Stufe besser.

---

## 4. Das Universum (Welt-Generierung)

Kein Planet ist gleich. Jeder Zielort wird aus 3 Komponenten (Traits) generiert.
Planeten sieht man an sich nicht, Infos tauchen auf taktischem Bildschirm auf. Wie in einem Missionsraum. (Dispatch macht das gut)

### Das 3-Trait-System
`[BIOM] + [STATUS] + [BEWOHNER]`

#### A. Biom (Die Umgebung)
* **Arid:** Hoher Energieverbrauch.
* **Toxic:** Benötigt Schutzanzüge. Ohne Schutz: 20% HP Verlust durch Besuch, 40% wenn Mission zu lange geht.
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

### Stats
**HP:** Leben
**Offensive:** Attackstärke (Ausgerüstet Waffe gibt Multiplikator an)
**Defensive:** Schadensreduzierung (Ausgerüstet Tech und Rüstung verstärkt den Wert)
**Diplomatie:** Naja erklärt sich von selbst
**Wissen:**
**Weisheit:** 
**Speed:** Schnittspeed gibt Boni oder Mali auf Missionsdauer. Manche Missionen sind nur Erfolgriech wenn sie das schaffen
**Alter:**
**Klasse:**
**Name:**
**Volk:**
**Besondere Traits:** 0-N
**IsUnique:** bool ob Unique ist?
**Rang:**
**Stresslevel:** Schlimme Dinge und Dauernd Missionen erhöhen es. Wird in Basis abgebaut pro Runde
**Inventar:** Möglichkeit AUsürtung zuzuweisen. Je ein Offensive, ein Deffensiv und ein Tech Gegenstand
**Missionslog:** Welche Missionen war dabei und war Erfolg oder nicht

Die Startstats sind Bedingt zufällig und hängen von der Klasse ab. Danach kann man mehr oder weniger mit jedem Besatzungsmitglied alles machen, also sprich umlernen, aber die Basisklasse bleibt bestehen. 

### Crew Klassen
* **Vanguard (Soldat):** Kampfbonus, schwere Rüstung. Wichtig für Verteidigung.
* **Scholar (Wissenschaftler):** Hackt Terminals, Bonus auf Forschung in der Basis.
* **Diplomat:** Schaltet Handlungsoptionen frei.
* **Engineer:** Repariert Ausrüstung und Basis-Systeme.
* **Spy:** Heimlichkeit, Sabotage

*Ränge:* Jede Char hat Ränge und die Unqiue können sogar einen Rang noch höher befödert werden. 

### Unique Heroes ("Stars")
Besondere Charaktere mit Backstory und *fixen* Traits.
* **Xeno-Hasser:** Schwäche auf Demokratie mit anderen Rassen, aber dafür offensiv einen Bonus von Stufenlevel x 5%
* **Alte Garde:** Haben in Missionen eine höhere Erfolgschance, aber bekommen langsamer XP
* **Jinx:** Zufallsereignisse sind tendenziell gravierender, aber dafür belohnender. XP und Beute Boni +20%
* **Kirk:** Durch romantische Beziehungen zu so gut wie allen Völkern gibt es auf Diplomatie einen Bonus von Stufenlevel X 5%
* uvm...

### Das Dispatch-Interface
Kein 3D-Kampf, sondern taktisches UI (Gesundheit, Stress, Munition).

**Entscheidungs-Loop:**
1.  *Alert:* "Feindkontakt: Patrouille der Synod."
2.  **[Option A - Vanguard]:** Hinterhalt (70% Erfolg).
3.  **[Option B - Diplomat]:** Bestechung (Kosten: 50 Gold).
4.  **[Option C]:** Rückzug!

> *Note:* Erfolg hängt von Crew-Stats und Vorbereitung (Briefing) ab. Wenn eine Mission scheitert kann was schlimmes passieren und Stress steigt stark. In schlimmen Fällen kann ein Besatzungsmitglied sterben.

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
* **Coalition:** Alle Fraktionen verbünden (Diplomatie-Sieg) -> Fast unmöglich durch ErzfeindSystem.

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
