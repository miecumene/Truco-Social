# Game Design Document: Social Truco 3D

## 1. Executive Summary

Social Truco 3D is a multiplayer, social-first adaptation of the traditional Latin American card game "Truco." Set in a stylized 3D environment, the game emphasizes human interaction, psychological warfare, and bluffing over pure card mechanics. Players gather in virtual bars to compete in 2v2 matches, using a dedicated "Gesture System" to communicate secret signals to teammates while deceiving opponents through proximity voice chat and expressive avatars.

## 2. Core Game Loop

- Join/Create Table: Players enter a 3D lobby and sit at a 4-chair table (2 teams of 2).
- The Deal: Each player receives 3 cards from a 40-card Spanish deck.
- Interaction Phase: Players use voice, text, and physical gestures (Signals) to coordinate or bluff.
- Betting & Play: Players play cards across three rounds while betting on "Envido" (points) or "Truco" (match stakes).
- Resolution: Points are tallied; first team to 30 points wins.
- Progression: Earn XP and Currency to unlock cosmetic rewards.

## 3. Mechanics & Ruleset

### 3.1. Card Hierarchy (Truco Power)

The game utilizes a standard 40-card Spanish deck. The power ranking (High to Low) is:

1. 1 of Swords (Ancho de Espadas)
2. 1 of Clubs (Ancho de Bastos)
3. 7 of Swords
4. 7 of Gold
5. All 3s
6. All 2s
7. 1 of Cups & 1 of Gold
8. All 12s, 11s, 10s, 7s (Cups/Clubs), 6s, 5s, 4s.

### 3.2. Betting Systems

- Envido: A side-bet based on card values of the same suit. Commands: Envido, Real Envido, Falta Envido.
- Truco: The main bet on who wins the best-of-three rounds. Commands: Truco, Re-Truco (3 points), Vale Cuatro (4 points).

## 4. Social Interaction System

### 4.1. Traditional Signal System (Gestures)

To replicate authentic Truco play, players can trigger specific facial animations to signal their hand to their partner. These are mapped to a Quick-Access Radial Menu.

| Card | Traditional Signal | In-Game Trigger | Animation Asset |
|------|--------------------|-----------------|-----------------|
| 1 of Swords | Raise Eyebrows | Menu -> Up | anim_brows_up |
| 1 of Clubs | Wink one eye | Menu -> Right | anim_wink |
| 7 of Swords | Smirk/Side-mouth | Menu -> Left | anim_smirk_L |
| 7 of Gold | Smirk/Side-mouth | Menu -> Down | anim_smirk_R |
| All 3s | Bite lower lip | Menu -> Center | anim_bite_lip |
| All 2s | Pout/Kiss face | Menu -> Secondary | anim_kiss |
| Bad Cards | Close eyes/Blink | Menu -> Tertiary | anim_blink_long |

### 4.2. Communication Tools

- Proximity Voice Chat: Audio volume attenuates based on 3D distance.
- Bluff Chat: Pre-set phrases (e.g., "I have nothing!", "Quiero!") with animated text bubbles over avatars.
- Emotes: Non-tactical social expressions (Laughing, Table Slap, Toast with glass).

## 5. Visual & Technical Design

### 5.1. Art Style

- Aesthetic: "Stylized Cozy." Low-to-mid poly models with soft lighting and pastel color palettes.
- Camera: Dynamic Cinemachine system. Defaults to a focused view of the player's hand, switching to a wide "Table View" or "Opponent Focus" during big bets.

### 5.2. Customization (Monetization & Retention)

- Avatars: Mix-and-match clothing (hats, shirts, glasses) on a standardized base mesh to ensure animation compatibility.
- Card Skins: Customizable card backs and front-face illustrations (e.g., Cyberpunk deck, Classic deck, Gold Foil).
- Table Environments: Unlockable rooms (Traditional Cantina, Beach Club, Underground Vault).

## 6. Technical Architecture (Unity Implementation)

### 6.1. Networking (Netcode for GameObjects)

- Authoritative Server: The server handles deck shuffling and point calculation to prevent cheating.
- RPCs (Remote Procedure Calls): Used for triggering gestures and betting voice-lines across all clients simultaneously.

### 6.2. Data Management (ScriptableObjects)

- Card Data: Stores ID, Suit, Value, and Truco/Envido weight.
- Match State: Manages the turn-based logic, current bet multiplier, and score tracking.

## 7. Progression System

- Experience Points (XP): Awarded for games played, with bonuses for wins and "Successful Bluffs" (winning a hand where the opponent folded a superior hand).
- Levels: Progression unlocks new signals, cosmetic slots, and higher-stakes rooms.
- Daily Challenges: e.g., "Win 3 hands with a 'Vale Cuatro' call" or "Signal your partner 5 times." 

## 8. Development Roadmap

- Phase 1 (Prototype): Basic 2v2 card logic and turn synchronization.
- Phase 2 (Social): Implementation of the Gesture Radial Menu and Proximity Chat.
- Phase 3 (Visuals): Integration of stylized avatars and environment assets.
- Phase 4 (Meta): Shop, Currency, and Cloud Save integration.
