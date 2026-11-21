# BURJ KHALIFA: DUBAI OPEN WORLD — Stage 1 Playable Demo

Unity 2022.3 LTS (3D Built-in template) recommended. Uses zero imported assets: the city is built at runtime.

## Run in Editor
1. Unity Hub -> New project -> 3D (Built-in Render Pipeline), Unity 2022.3 LTS. Add Android Build Support (SDK/NDK/OpenJDK) in the installer.
2. Copy `Assets/_Project` from this zip into your project's Assets folder.
3. Project Settings -> Player -> Other Settings -> Active Input Handling = "Input Manager (Old)" (or Both).
4. Open any scene (SampleScene) and press Play. GameManager auto-boots.
   Editor keys: WASD move, right-mouse drag look, Q switch character, E enter/exit car, Space brake.

## Build the APK
1. File -> Build Settings -> Android -> Switch Platform. Add the open scene to "Scenes In Build".
2. Player Settings: Company/Product name; Package Name e.g. com.yourname.burjdubai; Minimum API 24; Scripting Backend IL2CPP; Target Architectures ARM64 only; Graphics API OpenGLES3 (+Vulkan optional); Orientation Landscape.
3. Quality: Android level with Shadow Distance 60, Anti-aliasing 2x or off, VSync off.
4. Build Settings -> Build (APK) -> choose output folder. Install: `adb install -r BurjDubai.apk`.
For Play Store use a keystore (Publishing Settings) and Build App Bundle (.aab).

## Controls (touch)
Left side drag = move joystick. Right side drag = camera. SWITCH = change character. CAR = enter/exit nearest car. BRAKE = brake.

## Size/performance notes
- Static batching on city, shared materials, hard shadows, 60 m shadow distance, fog hides far clip (500 m).
- This demo APK will be ~25-40 MB, not 500 MB. Size grows only when real models/textures/audio are added (Stages 4-6).

## Roadmap (build and test one stage at a time)
- Stage 1 (this): city grid, Burj placeholder, 2 characters + switching, car, traffic, day/night, checkpoint mission, touch controls.
- Stage 2: motorcycles, wheel-collider physics, car sounds, pedestrians (NavMesh), traffic lights.
- Stage 3: mission system (ScriptableObject missions, dialogue, map/minimap), save/load.
- Stage 4: real Burj Khalifa + city models, URP, baked lighting, LODs, occlusion culling.
- Stage 5: animated humanoid characters (Mixamo/own rigs), UI Canvas, settings menu.
- Stage 6: texture compression (ASTC), addressables, profiling on mid-range devices.
