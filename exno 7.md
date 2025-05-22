# AI Random Roam with Chase - Unreal Engine

## 🎯 Aim
To create an AI character in Unreal Engine that roams randomly within a NavMesh area and chases the player when they come within a certain range, using Behavior Trees, Blackboard, and AI Perception.

## 🛠 Procedure

1. *Setup Navigation*
   - Add a NavMeshBoundsVolume to your level and scale it to cover the roamable area.
   - Press *P* to confirm the green nav area is visible (indicating navigable space).

2. *Create AI Character*
   - Create a Blueprint character (e.g., BP_AIEnemy) with a skeletal mesh and AIController class.
   - Create an AI Controller Blueprint (e.g., BP_AIController) and assign it to the character.

3. *Enable AI Perception*
   - In BP_AIController, add an AIPerception component.
   - Configure a *Sight* sense (set detection range, lose sight range, peripheral vision angle).
   - Bind OnPerceptionUpdated to update a blackboard value (e.g., CanSeePlayer and PlayerActor).

4. *Set Up Blackboard*
   - Create a Blackboard with the following keys:
     - TargetLocation (Vector)
     - PlayerActor (Object)
     - CanSeePlayer (Bool)

5. *Create Behavior Tree (BT_AI)*
   - Structure it like this:

     
     Root
     └── Selector
         ├── Sequence (Chase Player)
         │   ├── Blackboard Check: CanSeePlayer == true
         │   └── Move To: PlayerActor
         └── Sequence (Random Roam)
             ├── Task: Find Random Location → TargetLocation
             └── Move To: TargetLocation
     

6. *Custom Task: Find Random Location*
   - Create a new BTTask_BlueprintBase to get a random reachable point using:
     cpp
     UNavigationSystemV1::GetRandomReachablePointInRadius()
     
   - Set the result to the TargetLocation blackboard key.

7. *Test the AI*
   - Add a player character to the level.
   - Place the AI enemy in the map and assign its controller and behavior tree.
   - Press *Play*: the AI should roam when the player is far and chase the player when within sight.
  

## Output

![Screenshot 2025-05-15 103308](https://github.com/user-attachments/assets/9ec08412-d028-409d-9406-f88c29d8d854)

![Screenshot 2025-05-15 103442](https://github.com/user-attachments/assets/a8d84f39-4b48-43a7-9d85-66c63d5e8566)

![Screenshot 2025-05-09 105437](https://github.com/user-attachments/assets/da7e454b-1c33-4aad-98ad-5a95929a121b)

## ✅ Result
The AI character roams randomly within a defined area. When the player enters its sight range, the AI stops roaming and begins to chase the player until the player is out of sight, after which it resumes roaming.
