Developer Technical Brief: GEO Lab Dashboard
1. Project Overview
The GEO Lab Experiment Manager is a specialized Single-Page Application (SPA) designed to facilitate "Generative Engine Optimization" (GEO) testing. Unlike traditional SEO tools, this application focuses on scientific rigor, requiring the definition of multi-dimensional KPIs (Visibility, Accuracy, Position, etc.) before results are recorded.
2. Technical Stack
Frontend Framework: Vanilla JavaScript (ES6+).
Styling: Tailwind CSS (via CDN) for responsive utility-first design.
Data Visualization: Chart.js (Canvas-based) for radar and line-graph analysis.
Typography: Google Fonts (Inter).
Architecture: Single HTML file (SPA) with a sidebar-driven section-switching mechanism.
3. Information Architecture
The application is structured into logical modules that mirror a scientific research paper:
Dashboard (Summary): High-level view of active experiments and metric deltas.
Experiment Setup: The "Laboratory" entry where IF/THEN/BECAUSE logic is defined alongside a KPI Measurement Matrix.
Prompt Library: Intent mapping (Informational, Comparison, etc.) to test AI responses.
Implementation Log: A methodology tracker for technical changes (Schema, Fluency, Citations).
Results Analysis: Comparative visualization (Baseline vs. Post-Test).
Findings: Final qualitative verdict and next-step iterations.
4. Key Implementation Details
State Management
The application uses a central state object to manage data. This structure is designed to be easily extensible to a JSON API or local storage backend.const state = {    currentSection: 'dashboard',    prompts: [...], // Objects containing query, category, baseline, and goal    kpis: [...]     // Metrics targets and thresholds};
Navigation Logic
Navigation is handled via a navTo(sectionId) function that toggles the hidden class on section elements and manages CSS state for the sidebar buttons.
Visualization Engine
Radar Chart: Used for the "Balanced Scorecard" to show trade-offs between qualitative (Accuracy/Sentiment) and quantitative (Visibility/Position) metrics.
Line Chart: Implements a reversed Y-axis to track "Position" (where 1 is the highest/best rank).
Responsive Containers: All charts are wrapped in relative divs with maintainAspectRatio: false to ensure they adapt to grid layouts without breaking.
5. Potential Extension Areas
For a developer looking to expand this prototype:
Firestore Integration: The current state object is ready to be mapped to a /experiments collection in Firestore for persistence.
API Polling: One could integrate the "Prompt Library" with an LLM API (like Gemini or OpenAI) to automate the "Current Visibility" checks.
Export to PDF: Implementation of jspdf to allow researchers to export the final "Verdict" section as a formal case study.
Multi-Engine Comparison: Expanding the KPI matrix to compare performance across different LLMs (Perplexity vs. SearchGPT vs. Gemini) simultaneously.