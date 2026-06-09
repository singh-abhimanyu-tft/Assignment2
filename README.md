# C++ DLL Automation & Reverse Engineering Assignment
## UPDATED - UI Automation Only | Hard Deadline: Tomorrow 10 AM

---

## ⏰ CRITICAL DEADLINE
**Submission Deadline: Tomorrow Morning 10:00 AM**
- No submissions will be accepted after 10 AM
- Record video proof before deadline
- All deliverables must be ready

---

## 🎯 Assignment Overview

Create a C++ application that automates changing Microsoft Edge's default search engine **via UI interaction only** (no registry/preference file manipulation).

---

## ⚙️ Technical Requirements

### 1. UI Automation Only
**Important:** The entire solution must use **UI automation techniques ONLY**
- ✅ Automated mouse clicks
- ✅ Keyboard input simulation
- ✅ Window/control identification (using UI Automation API, AutoHotkey, or similar)
- ❌ NO registry modifications
- ❌ NO preference file editing
- ❌ NO Direct preference/secure preference manipulation
- ❌ NO encryption/decryption of settings

### 2. Non-Admin Requirement
**Entire solution must work WITHOUT Administrator privileges**
- ✅ Double-click to run as normal user
- ❌ NO UAC elevation requests
- ❌ NO admin-only API calls
- ❌ NO privilege escalation

---

## 📋 Deliverables Structure

### Part 1: C++ Solution

#### EXE Responsibilities:
- Load and execute the DLL
- Write logs to `%APPDATA%\EdgeAutomation\` folder
- Log entries:
  - Start Time
  - End Time
  - Status (Success/Failure)
  - Total Time Taken
- Run by double-clicking (no cmd, no admin)

#### DLL Responsibilities:
- Automate **Bing → Yahoo** search engine change
- Use **UI automation only** (mouse clicks, keyboard input, window detection)
- Return Success/Failure status to EXE
- **Must be reversible** (so it can be patched via reverse engineering)
- Ensure change persists after Edge restart

---

## 🔍 Reverse Engineering Task

### Using Ghidra or IDA:
1. Reverse engineer the compiled DLL
2. Identify the automation logic
3. Modify the DLL to change **Yahoo → DuckDuckGo** instead
4. No need to recompile - patch the binary directly if possible, OR recompile modified source

### Key Points:
- Allowed tools: **Ghidra Free**, **IDA Free**, or **IDA Pro**
- Show your analysis in the video
- Demonstrate the modification process

---

## 📹 Video Recording (Required)

**Record using Bandicam Free or similar:**

### Video Must Show (Continuous, Unedited):
1. ✅ Original EXE execution
2. ✅ Edge settings before automation
3. ✅ EXE running → UI automation changes Bing to Yahoo
4. ✅ Edge settings after automation (Yahoo confirmed)
5. ✅ Restart Edge → Yahoo persists
6. ✅ DLL analysis in Ghidra/IDA
7. ✅ DLL modification process
8. ✅ Modified EXE execution
9. ✅ UI automation changes Bing to DuckDuckGo
10. ✅ Edge settings after modification (DuckDuckGo confirmed)
11. ✅ Restart Edge → DuckDuckGo persists

### Recording Rules:
- **Continuous & unedited** (no cuts/editing)
- **Max 10 minutes**
- Clear audio/screen visibility
- Show timestamps if possible

---

## 📦 Final Deliverables (Due Tomorrow 10 AM)

### Code Files:
- [ ] EXE source code (C++)
- [ ] DLL source code (C++)
- [ ] Compiled EXE (.exe file)
- [ ] Original compiled DLL (.dll file)
- [ ] Modified DLL (.dll file - after reverse engineering patch)

### Documentation:
- [ ] Brief explanation of implementation approach
- [ ] Reverse engineering approach summary
- [ ] UI automation technique used (e.g., Windows UI Automation API, AutoHotkey, etc.)

### Proof:
- [ ] Video recording (MP4, max 10 min, unedited)

---

## 🛠️ Suggested Implementation Approach

### For UI Automation:
**Option 1: Windows UI Automation API (Native C++)**
```
- Use IUIAutomation interface
- Identify Edge Settings window/controls
- Simulate clicks and keyboard input
- Cross-platform reliable approach
```

**Option 2: Keyboard Simulation + Window Detection**
```
- SendInput() API for keyboard/mouse
- FindWindow() / FindWindowEx() for window detection
- SendMessage() for control interaction
```

**Option 3: Third-party (if allowed)**
```
- AutoHotkey (external, not ideal for C++ DLL)
- Not recommended for this assignment
```

**Recommended: Option 1 (Windows UI Automation API)**

---

## ✅ Verification Checklist

Before submitting:
- [ ] EXE runs with double-click (no admin prompt)
- [ ] EXE successfully loads DLL
- [ ] DLL automation works (Bing → Yahoo via UI)
- [ ] Logs written to AppData with timestamps
- [ ] Change persists after Edge restart
- [ ] DLL can be reverse engineered (intentional)
- [ ] Modified DLL changes Yahoo → DuckDuckGo via UI
- [ ] Video shows entire process unedited
- [ ] Video is under 10 minutes

---

## 🚨 IMPORTANT NOTES

### UI Automation Specifics:
- Must interact with Edge Settings UI **visibly** (user sees it happen)
- Cannot silently manipulate files/registry
- Edge must actually open Settings dialog
- User (or video) shows search engine dropdown changes

### Non-Admin Constraint:
- Test by running from normal user account
- No "Run as Administrator" shortcuts
- No UAC prompts should appear

### Deadline is Hard:
- **10 AM Tomorrow - No Extensions**
- Video proof required
- All source + binaries ready

---

## Questions to Clarify Before Starting:

1. Should the UI automation be visible on screen (clicks/keyboard visible), or can it be "stealth"?
2. Can we use AutoHotkey as helper, or must be pure C++?
3. Are there Edge instances that might already be running? (handle them?)
4. Should DLL check if Edge is installed before attempting automation?

---

**Good luck! You've got this. Show the process in video, make it work without admin, and reverse-engineer the DLL tomorrow. 🎯**
