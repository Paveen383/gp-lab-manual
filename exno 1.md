# Material Effects in Unreal Engine

## Aim
To implement and demonstrate various material effects in Unreal Engine, including emissive, roughness, and metallic properties, using the Material Editor.

## Procedure

1. *Create a New Material:*
   - Open Unreal Engine.
   - In the Content Browser, right-click and select *Material*.
   - Name it M_EffectsDemo.

2. *Apply Base Color:*
   - Open the material.
   - Add a *Vector Parameter* or *Constant3Vector* node and connect it to the *Base Color* input.

3. *Add Emissive Effect:*
   - Add a *Multiply* node.
   - Connect a *Constant3Vector* (for emissive color) and a *Scalar Parameter* (for intensity).
   - Connect the result to the *Emissive Color* input.

4. *Control Roughness:*
   - Add a *Scalar Parameter* node and connect it to the *Roughness* input.
   - Lower values = shinier surface, higher values = rougher surface.

5. *Control Metallic Property:*
   - Add a *Scalar Parameter* node and connect it to the *Metallic* input.
   - 0 = non-metal, 1 = fully metallic.

6. *Save and Apply Material:*
   - Save the material.
   - Apply it to any mesh in the scene (like a sphere or cube) to preview the results.
  
     
## Output
![Screenshot 2025-05-08 104047](https://github.com/user-attachments/assets/dcfd8d23-006e-44e6-9d4d-e7f379313404)
![Screenshot 2025-05-08 104202](https://github.com/user-attachments/assets/b25264c1-1f68-44c0-be93-c63d9e9ad5bc)
![Screenshot 2025-05-08 104853](https://github.com/user-attachments/assets/b5cc510a-428a-4fa9-a14c-c92ac3f70947)
![Screenshot 2025-05-08 105221](https://github.com/user-attachments/assets/3cd59079-4e09-406d-bf13-f3b4762ec985)


## Result
Successfully implemented a material in Unreal Engine showcasing:
- Emissive glow using emissive color and intensity.
- Variable surface roughness to simulate different textures.
- Metallic appearance adjustment to reflect light like real-world metals.

This setup enables dynamic, realistic materials suitable for use in environments, characters, and VFX in Unreal Engine projects.
