# Changelog

## [1.0.0-worldcraft] – 2026-11-18

### Rebranded
- Project renamed from "Speech-to-World Unity Client" to **WorldCraft AI – Create Your Own Universe**
- Product name updated in Unity Player Settings
- Company name updated to WorldCraft AI Studio
- Android Bundle ID updated to `com.worldcraftai.createyouruniverse`
- README completely rewritten for Meta VR Competition 2026

### Configuration Fixed
- Removed hardcoded developer path from `api.json` (`/home/h/Documents/dev/...`)
- Replaced `127.0.0.1` with example LAN IP `192.168.1.100` to remind users to set their server IP
- Added `api.example.json` as a template for new setup
- Added VR Creator scene to EditorBuildSettings

### Documentation Added
- `COMPETITION_NOTES.md` – competition checklist, build instructions, blockers
- `CHANGELOG.md` – this file

### UI Text Improved
- Recording button: "Start Recording" → "Tap to Speak"
- Analysing state: "Analysing..." → "Transcribing..."
- Added AppName, AppTagline, WelcomeMessage constants to UIManager

### Preserved
- All original scenes: Desktop Creator, VR Creator, Speech Recognition
- All original scripts and AI backend integration
- All VR interaction systems (XR Interaction Toolkit, OpenXR)
- Original LICENSE (GPL-3.0)
- Original architecture and namespace (AiWorldGeneration)

## [pre-1.0] – Original "Speech-to-World" Project
- Original development by Fondation Campus Biotech Geneva
- In collaboration with EPFL Laboratory of Cognitive Neuroscience (LNCO)
- Repository: https://github.com/fcbg-hnp-vr/VR-Environment-GenAI-Unity
