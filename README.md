# PRG1203 — Java Pokémon Game

<p align="center">
  <b>A text-based, object-oriented Java Pokémon console application featuring trainer profiles, dynamic evolution mechanics, elemental type matchups, and turn-based battles against wild Pokémon and rival trainers.</b>
</p>

---

## 📌 Table of Contents
* [Overview](#-overview)
* [Key Features & Modules](#-key-features--modules)
* [Game Menu](#-game-menu)
* [Gameplay Details](#-gameplay-details)
* [Project File Structure](#-project-file-structure)
* [Technical Stack & Requirements](#-technical-stack--requirements)
* [How to Run](#-how-to-run)
* [Data Files](#-data-files)
---

## 🔍 Overview

The **PRG1203 Pokémon Game** is an object-oriented programming project developed in Java. The application provides an interactive console gaming experience where players can create a trainer profile, manage their Pokémon roster, engage in strategic turn-based battles, catch Pokémon with different Poké Balls, and compete for high scores on a local leaderboard. Progress is saved to local text files, so you can continue where you left off.

---

## 🧩 Key Features & Modules

* **User Management & Persistence (`UserManager.java`, `Player.java`, `PlayerStorageManager.java`):** Trainer profile creation and loading by name, with local flat-file data persistence (`players_data.txt`). Returning trainers are welcomed back and their Pokémon gain EXP.
* **Pokémon & Evolution System (`Pokemon.java`, `EvolutionData.java`, `PokemonArt.java`, `ViewPokemonDetails.java`):** Manages Pokémon attributes, ASCII art rendering, detailed status inspection, and level-based evolution paths (e.g. Charmander → Charmeleon → Charizard).
* **Combat Mechanics (`WildBattle.java`, `RivalBattle.java`, `TypeEffectiveness.java`, `Pokeball.java`):** Separate battle engines for wild encounters and rival trainers, with elemental strength/weakness calculations and Poké Ball capture logic.
* **Score & Status Tracking (`ScoreManager.java`, `TrainerStatusService.java`):** Tracks performance and saves high scores and trainer reports to external files (`top_scores.txt`, `trainer_status.txt`).
* **Data Loader (`DataLoader.java`):** Generates random wild Pokémon by rarity tier (Common, Uncommon, Rare, Legendary) with randomised type, move type, HP and power.

---

## 🎮 Game Menu

| # | Option | Description |
|---|--------|-------------|
| 1 | Catch Pokémon | Choose one of 3 randomly generated wild Pokémon to add to your collection |
| 2 | View Collection | List all of your Pokémon |
| 3 | Wild Battle | Fight, catch or run away from a wild Pokémon |
| 4 | Rival Battle | Take on a rival's 2 Pokémon with 2 of your own and earn score points |
| 5 | Check Evolution | See which Pokémon can evolve and how many levels remain |
| 6 | Heal All Pokémon | Restore HP for your whole team |
| 7 | Release Pokémon | Return a Pokémon to the wild |
| 8 | View Top Scores | Show the leaderboard |
| 9 | Trainer Status | Show and export your trainer summary |
| 10 | View Pokémon Details | Inspect a single Pokémon |
| 11 | Save & Exit | Save progress and quit |

---

## ⚔️ Gameplay Details

**Poké Balls**

| Ball | Catch Rate |
|------|-----------|
| Poké Ball | 50% |
| Great Ball | 75% |
| Ultra Ball | 85% |
| Master Ball | 100% |

**Wild Pokémon rarity**

| Tier | Approx. chance |
|------|---------------|
| Common | ~60% |
| Uncommon | ~25% |
| Rare | ~12% |
| Legendary (Mew, Mewtwo, Rayquaza) | ~3% |

**Rival Battle scoring:** 50 points per duel won, 50 points per Pokémon that remains unfainted, plus a 30-point rival bonus. Scores are saved to the leaderboard.

---

## 📂 Project File Structure

```text
PRG1203_PokemonGame/
│
├── src/
│   ├── DataLoader.java             # Random wild Pokémon generator (rarity tiers)
│   ├── EvolutionData.java          # Pokémon evolution stages and level triggers
│   ├── Main.java                   # Main application entry point & game loop
│   ├── Player.java                 # Player profile and Pokémon collection
│   ├── PlayerStorageManager.java   # Local storage and persistence handler
│   ├── Pokeball.java               # Poké Ball types and catch rates
│   ├── Pokemon.java                # Core Pokémon attributes and logic
│   ├── PokemonArt.java             # Console ASCII art and visual renders
│   ├── RivalBattle.java            # Rival trainer combat logic and scoring
│   ├── ScoreManager.java           # Leaderboard and score tracking
│   ├── TrainerStatusService.java   # Trainer status report generator/exporter
│   ├── TypeEffectiveness.java      # Elemental type matchup calculator
│   ├── UserManager.java            # Trainer login / account creation
│   ├── ViewPokemonDetails.java     # Detailed Pokémon stats interface
│   └── WildBattle.java             # Wild encounter battle loop
│
├── players_data.txt                # Saved trainer records and their Pokémon
├── top_scores.txt                  # High score records
└── trainer_status.txt              # Exported trainer status reports
```

---

## 🛠 Technical Stack & Requirements

* **Language:** Java (JDK 14 or newer, as the code uses `switch` arrow syntax)
* **Interface:** Console / terminal (UTF-8 recommended for emojis and ASCII art)
* **Storage:** Local flat text files (no database required)
* **IDE (optional):** Eclipse or IntelliJ IDEA. The project includes Eclipse configuration.

---

## 🚀 How to Run

### Option 1 — Command line

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>/PRG1203_PokemonGame

mkdir bin
javac -encoding UTF-8 -d bin src/*.java
java -cp bin Main
```

> Run from the `PRG1203_PokemonGame` folder so the save files (`players_data.txt` etc.) are read and written in the right place.

### Option 2 — Eclipse

1. **File → Import → Existing Projects into Workspace**
2. Select the `PRG1203_PokemonGame` folder
3. Right-click `Main.java` → **Run As → Java Application**

> If emojis or ASCII art appear garbled, set the text file encoding to **UTF-8** (*Window → Preferences → General → Workspace*).

---

## 💾 Data Files

| File | Purpose |
|------|---------|
| `players_data.txt` | Trainer name followed by one Pokémon per line, entries separated by `---` |
| `top_scores.txt` | `trainer,score` entries for the leaderboard |
| `trainer_status.txt` | Human-readable trainer summaries (total Pokémon, strongest Pokémon, average level) |

