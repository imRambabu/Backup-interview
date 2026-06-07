🗂️ Project Overview
Name: Backup Admin Interview Prep Platform
Type: AI-Powered Single Page Application (React)
Purpose: Help Backup Administrators / Data Protection Engineers prepare for technical interviews

🛠️ Tech Stack
LayerTechnologyFrontendReact (JSX)StylingInline CSS + Google FontsAI EngineAnthropic Claude API (claude-sonnet-4)FontsSpace Mono + SyneHosting (recommended)Vercel / GitHub Pages

📦 6 Sections Explained
1. ⚙️ Operational Tasks

10 daily tasks a Backup Admin performs
Each task loads a full production procedure
Includes commands, verification, common issues

2. 🔧 Troubleshooting

20 real-world backup issues
Full RCA (Root Cause Analysis) workflow
Log file paths, commands, resolution steps

3. 💻 Commands

10 command categories
Commvault, NetBackup, Veeam, Linux, Windows
Copyable code blocks with explanations

4. 🏗️ Implementation

13 implementation guides
Prerequisites, steps, validation, rollback plan
Covers MediaAgent, Storage Policy, DR config

5. 🎯 Scenarios

Infinite AI-generated production scenarios
Select any technology from 14 options
Model answer reveal for 5+ YOE level responses

6. 🎤 Interview Mode

Live AI interviewer (L1 / L2 / L3 levels)
Real-time answer evaluation with score out of 10
Feedback on what's missing vs senior-level answer


🎯 Technologies Covered
Commvault · Veritas NetBackup · Veeam · NetApp · VMware vCenter · ESXi · Windows Server · Linux · Tape Libraries · AWS Backup · Azure Backup · Disaster Recovery · Deduplication · Backup Monitoring

🔌 How the AI Works
Every section makes a live call to the Anthropic API with a specialized system prompt tuned for that section's purpose — troubleshooting gets RCA-focused prompts, interview mode gets evaluator prompts, commands get syntax-focused prompts. Nothing is hardcoded — all content is generated fresh on demand.

📐 File Structure (if deployed)
backup-interview/
├── src/
│   ├── App.jsx          ← entire app (single file)
│   └── main.jsx         ← React entry point
├── public/
│   └── index.html
├── vite.config.js
├── package.json
└── .env                 ← ANTHROPIC_API_KEY (never commit this)

👥 Target Users

Backup Admin freshers preparing for L1 interviews
L2/L3 engineers brushing up for senior roles
Team leads creating interview question banks
Training teams onboarding new backup engineers


Want me to build the Next.js / Vercel-ready version with secured API key handling so you can deploy it publicly for free?Sonnet 4.6 Low
