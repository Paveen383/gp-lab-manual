# AI Random Roam - Unreal Engine

## Aim
To implement an AI character in Unreal Engine that roams randomly within a defined area using Behavior Trees and Navigation Mesh.

## Procedure

1. *Navigation Setup*
   - Add a NavMeshBoundsVolume to your level and scale it to cover the roamable area.
   - Ensure navigation is built (press *P* to visualize the navmesh).

2. *Create AI Character*
   - Create a new Character or Pawn Blueprint (e.g., BP_AICharacter).
   - Add an AIController Blueprint (e.g., BP_AIController) and assign it to your AI character.

3. *Set Up Behavior Tree*
   - Create a Behavior Tree (e.g., BT_RandomRoam) and a corresponding Blackboard.
   - Add a Blackboard Key (e.g., TargetLocation) of type Vector.

4. *Implement Roaming Logic*
   - In the Behavior Tree, use the following structure:
     - *Root* ➝ *Selector*
       - *Sequence*
         - Find Random Location (custom task to set TargetLocation)
         - Move To node (uses TargetLocation)
   - Create a custom BTTask Blueprint for finding a random location using UNavigationSystemV1::GetRandomPointInNavigableRadius.

5. *Place and Test*
   - Place your AI character in the level.
   - Assign the AI Controller and Behavior Tree.
   - Play the scene and observe the AI roaming randomly.



## Output

![Screenshot 2025-05-09 110157](https://github.com/user-attachments/assets/c7b895e7-b701-472c-9d79-cffa6b103f4b)

![Screenshot 2025-05-09 105953](https://github.com/user-attachments/assets/08205dcb-6f2c-4b51-b32f-eca31393904c)

![Screenshot 2025-05-09 110017](https://github.com/user-attachments/assets/a7e9b35a-9a07-4f22-9e35-ffc32db7054a)



## Result
The AI character successfully roams within the defined NavMesh area, choosing random destinations at intervals using the Behavior Tree logic.
