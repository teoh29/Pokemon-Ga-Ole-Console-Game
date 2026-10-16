# Pokemon-Ga-Ole-Console-Game

<p align="center">
  <b>A text-based, object-oriented Java Pokémon console application simulating user authentication, dynamic evolution mechanics, elemental type matchups, and turn-based battles against wild Pokémon and rival trainers.</b>
</p>

---

## 📌 Table of Contents
* [Overview](#overview)
* [Key Features & Modules](#key-features--modules)
* [Project File Structure](#project-file-structure)
* [Technical Stack & Requirements](#technical-stack--requirements)
* [How to Run](#how-to-run)
* [Contributors](#contributors)

---

## 🔍 Overview

The **PRG1203 Pokémon Game** is an object-oriented programming project developed in Java. The application provides an interactive console gaming experience where players can register accounts, manage their Pokémon roster, engage in strategic turn-based battles, track items using Pokéballs, and compete for high scores on a local leaderboard.

---

## 🧩 Key Features & Modules

* **User Management & Persistence (`UserManager.java`, `Player.java`, `PlayerStorageManager.java`):** Secure login and profile creation with local flat-file data persistence (`players_data.txt`).
* **Pokémon & Evolution System (`Pokemon.java`, `EvolutionData.java`, `PokemonArt.java`, `ViewPokemonDetails.java`):** Manages Pokémon attributes, visual ASCII rendering, detailed status inspectors, and milestone-based evolution paths.
* **Combat Mechanics (`WildBattle.java`, `RivalBattle.java`, `TypeEffectiveness.java`, `Pokeball.java`):** Distinct battle engines for wild encounters and trainer rivalries, incorporating elemental strength/weakness calculations and item-capturing logic[cite: 4].
* **Score & Status Tracking (`ScoreManager.java`, `TrainerStatusService.java`):** Tracks performance metrics and saves high scores to external records (`top_scores.txt`, `trainer_status.txt`)[cite: 4].
* **Data Loader (`DataLoader.java`):** Parses initialization and state data from local text files upon startup[cite: 4].

---

## 📂 Project File Structure

```text
PRG1203_PokemonGame/
│
├── src/
│   ├── DataLoader.java             # External resource and asset parser
│   ├── EvolutionData.java          # Pokémon evolution stages and triggers
│   ├── Main.java                   # Main application entry point & game loop
│   ├── Player.java                 # Player profile data and inventory
│   ├── PlayerStorageManager.java   # Local storage and persistence handler
│   ├── Pokeball.java               # Capture mechanics and item utilities
│   ├── Pokemon.java                # Core Pokémon attributes and logic
│   ├── PokemonArt.java             # Console ASCII art and visual renders
│   ├── RivalBattle.java            # NPC / Rival trainer combat logic
│   ├── ScoreManager.java           # Leaderboard and score tracking
│   ├── TrainerStatusService.java   # Active trainer state manager
│   ├── TypeEffectiveness.java      # Elemental type matchup calculators
│   ├── UserManager.java            # Authentication and account controls
│   ├── ViewPokemonDetails.java     # Detailed stats rendering interface
│   └── WildBattle.java             # Wild encounter battle loop
│
├── players_data.txt                # Saved user account records
├── top_scores.txt                  # Global / high score records
└── trainer_status.txt              # Active save state logs
