# Player Movement, Collectables, Health, and Score System in Unreal Engine

## Aim
To implement a basic player controller using the Character class in Unreal Engine, with movement controls, collectable items, a health system, and a score display.

## Procedure

### 1. Create Player Character with Movement
- Create a *Blueprint Class* based on Character (e.g., BP_PlayerCharacter).
- Add a *Camera* and *Spring Arm* for third-person or first-person view.
- In the *Event Graph*, add input bindings for movement:
  - *MoveForward, **MoveRight* using InputAxis events.
  - Use Add Movement Input for directional movement.

### 2. Create Collectable Item
- Create a new *Actor Blueprint* (e.g., BP_Collectable).
- Add a *Static Mesh* and *Sphere Collision* component.
- On BeginOverlap with player:
  - Destroy the collectable.
  - Call a custom event or function on the player to increment score or health.

### 3. Implement Health System
- In BP_PlayerCharacter, add a *Health* variable (e.g., float, default: 100).
- Create a *TakeDamage* function to subtract from Health.
- Optionally, implement logic to handle 0 health (e.g., death or respawn).

### 4. Implement Score System
- Add a *Score* variable (int) in BP_PlayerCharacter.
- When a collectable is picked up, increase the score.
- Display score using *UMG Widget*:
  - Create a Widget Blueprint (e.g., W_HUD).
  - Add *Text Blocks* bound to Health and Score variables.

### 5. Setup Game Mode
- Create a new *Game Mode Blueprint*.
- Set BP_PlayerCharacter as the default pawn.
- Set the HUD widget in the Game Mode’s BeginPlay using Create Widget and Add to Viewport.

## Output
![Screenshot 2025-05-09 102027](https://github.com/user-attachments/assets/5812ca92-a89a-4e57-b5ec-c7becb9da4cb)

![Screenshot 2025-05-09 102210](https://github.com/user-attachments/assets/09f640dc-8d88-4483-b845-2a2ebdf7b093)
![Screenshot 2025-05-09 104315](https://github.com/user-attachments/assets/42d5ca0b-5824-4136-877d-7c5293225884)
![Screenshot 2025-05-09 104446](https://github.com/user-attachments/assets/7c3f74f8-64ec-40e9-8839-5facfdda2a97)

## Result
A working prototype was developed with:
- Player movement using the Character class.
- Collectable items that increase score or health.
- A dynamic health system with logic for damage.
- On-screen UI displaying player health and score.

This system forms the basis for more advanced gameplay mechanics in Unreal Engine.
