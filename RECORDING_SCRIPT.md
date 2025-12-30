# EVE Quartermaster - 90 Second Demo Recording Script

## Recording Setup
- **Platform:** iOS Simulator or Android Emulator (or actual device)
- **Tool (iOS):** QuickTime Screen Recording or Xcode Simulator recording
- **Tool (Android):** Android Studio built-in recording or `scrcpy` + `peek`
- **Resolution:** Native mobile resolution (1080x1920 portrait or landscape)
- **FPS:** 30 (mobile should be smooth)
- **Duration:** 90 seconds
- **Output:** `demo.gif` or `demo.mp4`

## Pre-Recording Checklist
- [ ] App built and running on simulator/device
- [ ] At least 2 test characters configured with ESI tokens
- [ ] Test data populated (assets, market orders, etc.)
- [ ] Network connectivity working (ESI calls succeeding)
- [ ] Screen recording tool ready

---

## Shot-by-Shot Script (90 seconds)

### 0:00-0:15 | ESI Authentication Flow (15s)
**Action:**
1. App opens to login/splash screen
2. Show app logo and "EVE Quartermaster" branding
3. Tap **"Login with EVE SSO"** button
4. Browser/webview opens showing CCP's EVE SSO page
5. Show EVE Online login screen (can use pre-authenticated session)
6. Permission scopes screen appears briefly
7. Redirects back to app
8. Success! Dashboard loads

**Key Visual:** Professional OAuth flow, official CCP integration, seamless authentication

---

### 0:15-0:30 | Multi-Character Dashboard (15s)
**Action:**
1. Dashboard appears showing character cards:
   - Character portraits (from ESI)
   - Character names
   - Total ISK for each
   - Asset counts
   - Skill queue status
2. Scroll down showing 3-4 characters
3. Show total portfolio summary at top:
   - **Total ISK:** 5.2B
   - **Total Assets:** 1,247 items
   - **Active Orders:** 15
4. Tap on one character card to select

**Key Visual:** Multi-character management, rich data display, professional mobile UI

---

### 0:30-0:45 | Asset Tracking (15s)
**Action:**
1. Character selected → **Assets** tab loads
2. Shows categorized asset list:
   - **Jita 4-4** (152 items)
   - **Perimeter - Tranquility Trading Tower** (89 items)
   - **Amarr VIII** (45 items)
3. Tap **"Jita 4-4"** to expand
4. Scroll through items:
   - Ammunition
   - Ships (show ship icons)
   - Modules
   - Ore/minerals
5. Shows item quantities, estimated values
6. Quick filter: Type "Raven" → shows all Raven hulls across all locations

**Key Visual:** Asset tracking across multiple stations, fast search, data richness

---

### 0:45-0:60 | Route Planning - Initial (15s)
**Action:**
1. Tap bottom navigation → **"Route Planning"** tab
2. Clean route planner UI appears
3. **From:** Auto-filled with current character location "Jita"
4. Tap **To:** field
5. Type system name: "Amarr"
6. Autocomplete dropdown shows matches
7. Select "Amarr"
8. Toggle switch: **"Prefer safer routes"** (ON)
9. Tap **"Calculate Route"** button
10. Loading spinner (1-2 seconds)

**Key Visual:** Professional route planner UI, autocomplete, settings toggles

---

### 0:60-0:75 | AI Route Intelligence (15s)
**Action:**
1. Route calculated! Map view appears showing:
   - **21 jumps** via high-sec
   - Route line drawn on mini 2D map
2. System list below shows each jump with **danger ratings:**
   - ✅ **Jita** (Green - Safe)
   - ✅ **Perimeter** (Green - Safe)
   - ⚠️ **Uedama** (Red - 12 kills in 24h)
   - ✅ **Sivala** (Green - Safe)
   - ⚠️ **Niarja** (Yellow - 3 kills in 24h)
3. Scroll through system list
4. Tap on **Uedama** (high-danger system)

**Key Visual:** AI-powered danger ratings, zkillboard integration, intelligent risk assessment

---

### 0:75-0:90 | Threat Intelligence Detail (15s)
**Action:**
1. **Uedama** detail modal opens:
   - **Recent Kills:** 12 in last 24 hours
   - **Ganking Activity:** HIGH (red indicator)
   - **Typical Ship Lost:** Haulers, Freighters
   - Recent kill thumbnails from zkillboard
   - Timestamp of last kill: "2 hours ago"
2. **Alternative Route Suggestion:**
   - "Safer route available (+3 jumps, avoid Uedama)"
   - Tap **"Use Safer Route"** button
3. Route recalculates
4. New route: 24 jumps, no red systems
5. Success message: "Route updated - safer path selected"

**Key Visual:** Real-time threat intelligence, AI recommendations, zkillboard integration

---

## Post-Recording

### Convert to GIF (if recorded as MP4)
```bash
# iOS: Export from QuickTime as .mov, convert to GIF
ffmpeg -i demo.mov -vf "fps=20,scale=360:-1:flags=lanczos" -loop 0 demo.gif

# Android: Direct recording may produce MP4
ffmpeg -i demo.mp4 -vf "fps=20,scale=360:-1:flags=lanczos" -loop 0 demo.gif

# Optimize if too large
ffmpeg -i demo.gif -vf "fps=15,scale=360:-1:flags=lanczos" -y demo_optimized.gif
```

### Add to Repository
```bash
cp demo.gif /home/arete/projects/EVE_Quartermaster/demo.gif

# Update README.md (add at top after title)
# ![Demo](demo.gif)

git add demo.gif README.md
git commit -m "Add 90-second mobile capability demo"
git push origin main
```

---

## Recording Tips

**Mobile-Specific:**
- **Portrait orientation** recommended (standard mobile use)
- Keep fingers/touch indicators visible if possible (shows it's real touch interface)
- Smooth scrolling and taps (no frantic gestures)
- Show keyboard briefly when typing to prove it's real mobile input

**Data Display:**
- Use realistic EVE Online data (character names, ISK values, ship names)
- Can obscure personal character names if needed
- Make sure portraits load (cache them before recording)

**Timing Mobile Actions:**
- Account for network latency (ESI API calls)
- Pre-load data before recording heavy sections
- Use test environment with pre-populated cache if needed

**Polish:**
- Show iOS/Android native UI elements (status bar, navigation gestures)
- Rotate device to landscape briefly to show responsive design (optional)
- End on a clean, professional screen (not mid-action)

---

## Alternative: Use Expo Dev Tools Recording
If using Expo:
```bash
# Start app with recording enabled
expo start --dev-client

# Press 'i' for iOS simulator
# In simulator: Device → Trigger Screenshot / Record Screen
# Expo also has built-in screen recording in dev menu
```

---

## Recording Tool Installation

### iOS (Mac required):
```bash
# Use built-in QuickTime Player
# File → New Screen Recording → Select iPhone Simulator
```

### Android (Linux/Mac/Windows):
```bash
# Install scrcpy for Android screen mirroring
sudo apt install scrcpy  # Ubuntu/Debian
brew install scrcpy      # Mac

# Then record with peek or OBS pointing at scrcpy window
```

---

**Goal:** Viewer watches and thinks "This is a production-ready mobile app with real-time EVE integration and AI-powered intelligence."
