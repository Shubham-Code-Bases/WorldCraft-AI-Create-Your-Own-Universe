# WorldCraft AI – Meta VR Competition 2026 Notes

## Competition Entry
- **Project Name**: WorldCraft AI – Create Your Own Universe  
- **Category**: Productivity + Entertainment  
- **Platform**: Meta Quest (via Android/OpenXR build)
- **Unity Version**: 2022.3.36+

## ✅ Implemented & Working
- [x] Text-to-skybox AI generation (via Python backend)
- [x] Speech-to-text voice input (microphone recording → server transcription)
- [x] Skybox inpainting (draw mask → repaint selected area)
- [x] VR interaction (XR Interaction Toolkit, OpenXR)
- [x] Desktop fallback mode
- [x] TCP client-server communication
- [x] Configurable server IP/port (api.json)
- [x] VR Creator scene added to EditorBuildSettings
- [x] Android permissions configured (`INTERNET`, `RECORD_AUDIO`, cleartext HTTP support)
- [x] Android runtime microphone permission check in `AudioRecorder.cs`

## ⚠️ Remaining Requirements Before Submission
- [ ] **Hand Tracking**: Verified NOT currently installed (`com.unity.xr.hands` is absent from `Packages/manifest.json`).
  - To add for competition: Window → Package Manager → Add package by name: `com.unity.xr.hands`
  - In Project Settings → XR Plug-in Management → OpenXR: enable **Hand Tracking Subsystem**
  - If controllers-only is acceptable: document Touch Controllers as primary input mechanism
- [ ] **Build & Sign APK**: For official store/App Lab release, configure Android keystore in Player Settings (debug key works for developer sideloading)
- [ ] **Python Backend on LAN**: Start server on host PC and set `serverDefaultIp` in `api.json` to host's WiFi IPv4 address
- [ ] **Demo Video & Screenshots**: Record Quest gameplay and add to README placeholders

## 🏗️ Build Instructions (Android / Meta Quest)

### Prerequisites
1. Unity 2022.3.36+ with Android Build Support module
2. Android SDK/NDK (via Unity Hub)
3. Meta XR SDK or OpenXR + Oculus provider

### Steps
1. Open project in Unity Editor
2. Go to File → Build Settings
3. Switch Platform to Android
4. Add "VR Creator" scene to build (Scenes In Build)
5. Go to Edit → Project Settings → Player → Android tab
6. Set Bundle Identifier: `com.worldcraftai.createyouruniverse`
7. Set Minimum API Level: Android 10 (API 29)
8. Enable: IL2CPP scripting backend, ARM64 architecture
9. Connect Meta Quest via USB (developer mode enabled)
10. Click Build and Run, or Build to generate .apk

### Python Backend (Required for AI features)
1. Clone: https://github.com/fcbg-hnp-vr/VR-Environment-GenAI-Server
2. Set up Python environment and start the server
3. Update `Assets/Configurations/api.json` with your server's LAN IP
4. Ensure Quest and server are on the same WiFi network

## 🧪 Testing on Meta Quest
1. Install APK via `adb install WorldCraftAI.apk`
2. Launch from Unknown Sources in Quest library
3. Stand in open space, put on headset
4. VR Creator scene should load with the UI panel visible
5. Test voice input: press microphone button, speak world description
6. Test generation: press Generate button, wait for skybox to appear
7. Test inpainting: switch to Painting mode, draw on skybox, submit

## 🚫 Known Blockers
- Hand tracking not verified — test with controllers first
- Backend server must run on same LAN; Quest cannot reach localhost/127.0.0.1
- No offline mode; all AI features require the Python server
