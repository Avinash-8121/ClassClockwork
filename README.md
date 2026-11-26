# ClassClockwork: ZeroClash Timetable Generator

An automated, conflict-free academic timetable generator built with **React 18, TypeScript, Tailwind CSS, and Vite**, implementing an in-browser **Constraint Satisfaction Problem (CSP)** backtracking algorithm with the **Minimum Remaining Values (MRV)** heuristic.

---

## 🚀 Opening in Visual Studio Code

### Method 1: From the Command Line / Terminal
Open your terminal or PowerShell and run:
```bash
cd C:\Ccw
code .
```

### Method 2: From VS Code Directly
1. Launch **Visual Studio Code**.
2. Click **File** $\rightarrow$ **Open Folder...** (or press `Ctrl + K, Ctrl + O`).
3. Select the `C:\Ccw` directory and click **Select Folder**.

---

## 🛠️ Running the Project in VS Code

### Option A: Via Integrated Terminal (Standard Vite Dev Server)
1. Open the integrated terminal in VS Code (`Ctrl + \``).
2. Start the dev server:
   ```bash
   npm run dev
   ```
3. Click the local URL: **[http://localhost:5173](http://localhost:5173)**.

### Option B: 1-Click Launch with Debugging (`F5`)
1. Press `F5` in VS Code (or open the **Run & Debug** tab on the left).
2. Choose:
   - **Launch Dev Server in Chrome**: Starts the Vite server and attaches Chrome.
   - **Open Standalone HTML in Chrome**: Directly opens the zero-dependency single-file build in Chrome.

### Option C: Standalone HTML (Zero Server Required)
- Open [`ClassClockwork.html`](./ClassClockwork.html) directly in any browser:
  - Right-click `ClassClockwork.html` $\rightarrow$ **Open with** $\rightarrow$ **Google Chrome** (or drag it into a Chrome tab).

---

## 📂 Project Structure

```
Ccw/
├── .vscode/                     # VS Code workspace settings, launch & task configs
│   ├── settings.json            # TypeScript & Tailwind IntelliSense settings
│   ├── launch.json              # F5 Chrome debug configurations
│   ├── tasks.json               # Ctrl+Shift+B build and dev tasks
│   └── extensions.json          # Recommended VS Code extensions
├── src/
│   ├── components/
│   │   ├── Navbar.tsx           # Top navigation, view toggles, presets & export
│   │   ├── TimetableGrid.tsx    # 5x6 drag-and-drop interactive matrix
│   │   ├── ClashAuditor.tsx     # Real-time conflict inspector drawer
│   │   ├── ResourceManager.tsx  # CRUD for subjects, faculty availability, rooms, batches
│   │   ├── MetricsModal.tsx     # Gini index workload balance & room analytics
│   │   └── PrintView.tsx        # Structured printer & PDF export layout
│   ├── services/
│   │   ├── cspSolver.ts         # Recursive backtracking CSP solver with MRV heuristic
│   │   ├── clashDetector.ts     # Real-time conflict auditor (7 clash types)
│   │   └── exportService.ts     # Gini coefficient math, .ics iCal generator & file download
│   ├── data/
│   │   └── sampleData.ts        # Presets (Page 3 Hackathon Demo & CS Semester Dataset)
│   ├── types/
│   │   └── index.ts             # Strict TypeScript definitions
│   ├── App.tsx                  # Root application state & synchronization
│   ├── main.tsx                 # React DOM mount point
│   └── index.css                # Tailwind CSS base styles & print media rules
├── ClassClockwork.html          # Self-contained single-file HTML build (runs offline)
├── standalone.html              # Human-readable single-file HTML version
├── index.html                   # Vite entry HTML
├── package.json                 # Dependencies and build scripts
├── tsconfig.json                # TypeScript compiler configuration
├── tailwind.config.js           # Tailwind design tokens
└── vite.config.ts               # Vite bundler setup
```

---

## 🧪 Testing the Problem Brief Demo Scenario (Page 3)
1. In the top navigation bar, click **Presets** $\rightarrow$ **🚀 ZeroClash Demo (Page 3)**.
2. The CSP solver automatically allocates 6 subjects, 5 faculty, and 4 rooms (including the 3-hour OS lab) with **Zero Clashes**.
3. **Trigger Clash Detection**: Drag Dr. Sharma's lecture block into another slot where Dr. Sharma already teaches.
4. The system immediately flashes a red conflict badge:
   `Clash: Dr. Sharma already booked in Room 102 during [Day] [Period]`.
