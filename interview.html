import { useState, useRef, useEffect } from "react";

const SECTIONS = [
  { id: "operational", label: "Operational Tasks", icon: "⚙️", color: "#00d4ff" },
  { id: "troubleshooting", label: "Troubleshooting", icon: "🔧", color: "#ff6b35" },
  { id: "commands", label: "Commands", icon: "💻", color: "#a8ff3e" },
  { id: "implementation", label: "Implementation", icon: "🏗️", color: "#ff3eac" },
  { id: "scenarios", label: "Scenarios", icon: "🎯", color: "#ffe03e" },
  { id: "interview", label: "Interview Mode", icon: "🎤", color: "#b03eff" },
];

const TECHNOLOGIES = [
  "Commvault","Veritas NetBackup","Veeam Backup & Replication","NetApp Storage",
  "VMware vCenter","ESXi","Windows Servers","Linux Servers","Tape Libraries",
  "AWS Backup","Azure Backup","Disaster Recovery","Backup Monitoring","Deduplication",
];

const OPERATIONAL_TASKS = [
  "Daily backup monitoring","Failed backup troubleshooting","Missed schedules",
  "Backup SLA verification","Restore validation","Capacity monitoring",
  "Media management","Client installation","Client upgrades","Backup Reporting",
];

const TROUBLESHOOTING_TOPICS = [
  "Commvault backup failure","Commvault restore failure","MediaAgent offline",
  "DDB performance issue","DDB corruption","Auxiliary copy failure",
  "Job stuck in pending state","VMware snapshot failure","VSS writer failure",
  "Library offline","Tape drive down","NetBackup backup failure",
  "NetBackup restore failure","Client not communicating","Certificate issues",
  "Storage policy issue","Deduplication issue","Backup window exceeded",
  "Backup performance degradation","Database backup failure",
];

const IMPL_TASKS = [
  "New Client Installation","MediaAgent Installation","Disk Library Creation",
  "Storage Policy Creation","Schedule Policy Creation","Server Onboarding",
  "VMware vCenter Onboarding","DDB Creation","Auxiliary Copy Configuration",
  "Tape Library Configuration","Client Upgrade","CommServe Upgrade",
  "DR Backup Configuration",
];

function TypingIndicator() {
  return (
    <div style={{ display: "flex", gap: 5, alignItems: "center", padding: "12px 16px" }}>
      {[0,1,2].map(i => (
        <div key={i} style={{
          width: 8, height: 8, borderRadius: "50%", background: "#00d4ff",
          animation: `bounce 1.2s ease-in-out ${i * 0.2}s infinite`,
        }} />
      ))}
    </div>
  );
}

function CodeBlock({ code }) {
  const [copied, setCopied] = useState(false);
  return (
    <div style={{ position: "relative", margin: "8px 0" }}>
      <pre style={{
        background: "#0a0f1e", border: "1px solid #1a2540", borderRadius: 6,
        padding: "12px 16px", overflowX: "auto", fontSize: 12,
        fontFamily: "'JetBrains Mono', 'Fira Code', monospace",
        color: "#a8ff3e", lineHeight: 1.6, margin: 0,
      }}>{code}</pre>
      <button onClick={() => { navigator.clipboard.writeText(code); setCopied(true); setTimeout(() => setCopied(false), 2000); }}
        style={{
          position: "absolute", top: 8, right: 8, background: copied ? "#a8ff3e" : "#1a2540",
          color: copied ? "#000" : "#a8ff3e", border: "1px solid #a8ff3e",
          borderRadius: 4, padding: "2px 8px", fontSize: 11, cursor: "pointer",
          transition: "all 0.2s",
        }}>
        {copied ? "✓" : "Copy"}
      </button>
    </div>
  );
}

function formatResponse(text) {
  if (!text) return null;
  const lines = text.split("\n");
  const elements = [];
  let inCode = false;
  let codeLines = [];
  let key = 0;

  for (let i = 0; i < lines.length; i++) {
    const line = lines[i];
    if (line.startsWith("```")) {
      if (inCode) {
        elements.push(<CodeBlock key={key++} code={codeLines.join("\n")} />);
        codeLines = [];
        inCode = false;
      } else {
        inCode = true;
      }
      continue;
    }
    if (inCode) { codeLines.push(line); continue; }

    if (line.startsWith("### ")) {
      elements.push(<h4 key={key++} style={{ color: "#00d4ff", fontSize: 13, fontWeight: 700, margin: "14px 0 4px", fontFamily: "'Space Mono', monospace", textTransform: "uppercase", letterSpacing: 1 }}>{line.slice(4)}</h4>);
    } else if (line.startsWith("## ")) {
      elements.push(<h3 key={key++} style={{ color: "#ffe03e", fontSize: 15, fontWeight: 700, margin: "16px 0 6px", borderBottom: "1px solid #1a2540", paddingBottom: 6 }}>{line.slice(3)}</h3>);
    } else if (line.startsWith("**") && line.endsWith("**")) {
      elements.push(<p key={key++} style={{ color: "#ff6b35", fontWeight: 700, margin: "6px 0 2px", fontSize: 13 }}>{line.slice(2, -2)}</p>);
    } else if (line.startsWith("- ") || line.startsWith("• ")) {
      elements.push(<div key={key++} style={{ display: "flex", gap: 8, margin: "3px 0", paddingLeft: 8 }}>
        <span style={{ color: "#00d4ff", flexShrink: 0 }}>▸</span>
        <span style={{ color: "#c8d8e8", fontSize: 13, lineHeight: 1.5 }}>{line.slice(2)}</span>
      </div>);
    } else if (/^\d+\./.test(line)) {
      elements.push(<div key={key++} style={{ display: "flex", gap: 8, margin: "3px 0", paddingLeft: 8 }}>
        <span style={{ color: "#ff6b35", flexShrink: 0, fontWeight: 700, fontSize: 12 }}>{line.match(/^\d+/)[0]}.</span>
        <span style={{ color: "#c8d8e8", fontSize: 13, lineHeight: 1.5 }}>{line.replace(/^\d+\.\s*/, "")}</span>
      </div>);
    } else if (line.trim()) {
      elements.push(<p key={key++} style={{ color: "#c8d8e8", fontSize: 13, lineHeight: 1.6, margin: "4px 0" }}>{line}</p>);
    } else {
      elements.push(<div key={key++} style={{ height: 6 }} />);
    }
  }
  return elements;
}

// ─── SECTION PANELS ───────────────────────────────────────────────────────────

function OperationalPanel() {
  const [selected, setSelected] = useState(null);
  const [response, setResponse] = useState("");
  const [loading, setLoading] = useState(false);

  async function fetchTask(task) {
    setSelected(task);
    setResponse("");
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: "You are a Senior Backup Architect with 20+ years experience. Provide production-level operational procedures. Use markdown with ## headers, bullet points, and code blocks for commands. Be specific with real commands, log paths, and service names.",
          messages: [{ role: "user", content: `Provide a complete production procedure for: "${task}" in a Backup Administrator role. Include: Task Objective, Step-by-Step Procedure, Commands (in code blocks), Verification steps, Common Issues & Resolution.` }]
        })
      });
      const data = await res.json();
      setResponse(data.content?.[0]?.text || "No response.");
    } catch (e) { setResponse("Error fetching response."); }
    setLoading(false);
  }

  return (
    <div style={{ display: "flex", gap: 16, height: "100%" }}>
      <div style={{ width: 220, flexShrink: 0, overflowY: "auto" }}>
        <div style={{ fontSize: 11, color: "#4a6080", textTransform: "uppercase", letterSpacing: 2, marginBottom: 12, fontFamily: "'Space Mono', monospace" }}>Daily Tasks</div>
        {OPERATIONAL_TASKS.map(t => (
          <button key={t} onClick={() => fetchTask(t)} style={{
            display: "block", width: "100%", textAlign: "left", padding: "10px 14px",
            background: selected === t ? "#0d1f35" : "transparent",
            border: selected === t ? "1px solid #00d4ff" : "1px solid #1a2540",
            borderRadius: 6, color: selected === t ? "#00d4ff" : "#7a9ab8",
            fontSize: 12, cursor: "pointer", marginBottom: 6, transition: "all 0.2s",
            fontFamily: "'Space Mono', monospace",
          }}>{t}</button>
        ))}
      </div>
      <div style={{ flex: 1, overflowY: "auto", paddingLeft: 16, borderLeft: "1px solid #1a2540" }}>
        {!selected && <div style={{ color: "#2a4060", fontSize: 14, marginTop: 40, textAlign: "center" }}>← Select a task to load the procedure</div>}
        {loading && <TypingIndicator />}
        {!loading && response && <div>{formatResponse(response)}</div>}
      </div>
    </div>
  );
}

function TroubleshootingPanel() {
  const [selected, setSelected] = useState(null);
  const [response, setResponse] = useState("");
  const [loading, setLoading] = useState(false);

  async function fetchIssue(issue) {
    setSelected(issue);
    setResponse("");
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: "You are a Senior Backup Architect troubleshooting expert. Give production-level RCA and resolution. Use markdown with sections, code blocks for commands and log snippets.",
          messages: [{ role: "user", content: `Production troubleshooting guide for: "${issue}". Include: Symptoms, Environment, Investigation Steps (numbered), Commands (code blocks), Logs to Check (with file paths), Root Cause Analysis, Resolution Steps, Prevention Measures.` }]
        })
      });
      const data = await res.json();
      setResponse(data.content?.[0]?.text || "No response.");
    } catch (e) { setResponse("Error fetching response."); }
    setLoading(false);
  }

  return (
    <div style={{ display: "flex", gap: 16, height: "100%" }}>
      <div style={{ width: 220, flexShrink: 0, overflowY: "auto" }}>
        <div style={{ fontSize: 11, color: "#4a6080", textTransform: "uppercase", letterSpacing: 2, marginBottom: 12, fontFamily: "'Space Mono', monospace" }}>Issues</div>
        {TROUBLESHOOTING_TOPICS.map(t => (
          <button key={t} onClick={() => fetchIssue(t)} style={{
            display: "block", width: "100%", textAlign: "left", padding: "10px 14px",
            background: selected === t ? "#1f0d0d" : "transparent",
            border: selected === t ? "1px solid #ff6b35" : "1px solid #1a2540",
            borderRadius: 6, color: selected === t ? "#ff6b35" : "#7a9ab8",
            fontSize: 12, cursor: "pointer", marginBottom: 6, transition: "all 0.2s",
            fontFamily: "'Space Mono', monospace",
          }}>{t}</button>
        ))}
      </div>
      <div style={{ flex: 1, overflowY: "auto", paddingLeft: 16, borderLeft: "1px solid #1a2540" }}>
        {!selected && <div style={{ color: "#2a4060", fontSize: 14, marginTop: 40, textAlign: "center" }}>← Select an issue to investigate</div>}
        {loading && <TypingIndicator />}
        {!loading && response && <div>{formatResponse(response)}</div>}
      </div>
    </div>
  );
}

function CommandsPanel() {
  const [selected, setSelected] = useState(null);
  const [response, setResponse] = useState("");
  const [loading, setLoading] = useState(false);

  const categories = [
    { id: "commvault_win", label: "Commvault (Windows)" },
    { id: "commvault_linux", label: "Commvault (Linux)" },
    { id: "netbackup", label: "Veritas NetBackup" },
    { id: "veeam", label: "Veeam" },
    { id: "ddb", label: "DDB Commands" },
    { id: "media_agent", label: "MediaAgent" },
    { id: "tape", label: "Tape Library" },
    { id: "network", label: "Network Diagnostics" },
    { id: "linux_sys", label: "Linux System" },
    { id: "windows_sys", label: "Windows System" },
  ];

  async function fetchCommands(cat) {
    setSelected(cat.id);
    setResponse("");
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: "You are a Backup Admin commands expert. Provide real, production commands with explanations. Always put commands in code blocks. Include syntax, example output, and when to use each command.",
          messages: [{ role: "user", content: `List all essential production commands for: "${cat.label}" used by Backup Administrators. For each command provide: command (in code block), purpose, example usage, what to look for in output.` }]
        })
      });
      const data = await res.json();
      setResponse(data.content?.[0]?.text || "No response.");
    } catch (e) { setResponse("Error fetching response."); }
    setLoading(false);
  }

  return (
    <div style={{ display: "flex", gap: 16, height: "100%" }}>
      <div style={{ width: 200, flexShrink: 0, overflowY: "auto" }}>
        <div style={{ fontSize: 11, color: "#4a6080", textTransform: "uppercase", letterSpacing: 2, marginBottom: 12, fontFamily: "'Space Mono', monospace" }}>Categories</div>
        {categories.map(c => (
          <button key={c.id} onClick={() => fetchCommands(c)} style={{
            display: "block", width: "100%", textAlign: "left", padding: "10px 14px",
            background: selected === c.id ? "#0d1a0d" : "transparent",
            border: selected === c.id ? "1px solid #a8ff3e" : "1px solid #1a2540",
            borderRadius: 6, color: selected === c.id ? "#a8ff3e" : "#7a9ab8",
            fontSize: 12, cursor: "pointer", marginBottom: 6, transition: "all 0.2s",
            fontFamily: "'Space Mono', monospace",
          }}>{c.label}</button>
        ))}
      </div>
      <div style={{ flex: 1, overflowY: "auto", paddingLeft: 16, borderLeft: "1px solid #1a2540" }}>
        {!selected && <div style={{ color: "#2a4060", fontSize: 14, marginTop: 40, textAlign: "center" }}>← Select a category</div>}
        {loading && <TypingIndicator />}
        {!loading && response && <div>{formatResponse(response)}</div>}
      </div>
    </div>
  );
}

function ImplementationPanel() {
  const [selected, setSelected] = useState(null);
  const [response, setResponse] = useState("");
  const [loading, setLoading] = useState(false);

  async function fetchImpl(task) {
    setSelected(task);
    setResponse("");
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: "You are a Senior Backup Architect doing production implementations. Be specific with real steps, commands, and validation. Use markdown.",
          messages: [{ role: "user", content: `Complete implementation guide for Commvault: "${task}". Include: Prerequisites, Architecture Overview, Step-by-Step Configuration (with commands in code blocks), Validation Steps, Common Pitfalls, Rollback Plan, Post-Implementation Checks.` }]
        })
      });
      const data = await res.json();
      setResponse(data.content?.[0]?.text || "No response.");
    } catch (e) { setResponse("Error fetching response."); }
    setLoading(false);
  }

  return (
    <div style={{ display: "flex", gap: 16, height: "100%" }}>
      <div style={{ width: 220, flexShrink: 0, overflowY: "auto" }}>
        <div style={{ fontSize: 11, color: "#4a6080", textTransform: "uppercase", letterSpacing: 2, marginBottom: 12, fontFamily: "'Space Mono', monospace" }}>Tasks</div>
        {IMPL_TASKS.map(t => (
          <button key={t} onClick={() => fetchImpl(t)} style={{
            display: "block", width: "100%", textAlign: "left", padding: "10px 14px",
            background: selected === t ? "#1a0d1f" : "transparent",
            border: selected === t ? "1px solid #ff3eac" : "1px solid #1a2540",
            borderRadius: 6, color: selected === t ? "#ff3eac" : "#7a9ab8",
            fontSize: 12, cursor: "pointer", marginBottom: 6, transition: "all 0.2s",
            fontFamily: "'Space Mono', monospace",
          }}>{t}</button>
        ))}
      </div>
      <div style={{ flex: 1, overflowY: "auto", paddingLeft: 16, borderLeft: "1px solid #1a2540" }}>
        {!selected && <div style={{ color: "#2a4060", fontSize: 14, marginTop: 40, textAlign: "center" }}>← Select an implementation task</div>}
        {loading && <TypingIndicator />}
        {!loading && response && <div>{formatResponse(response)}</div>}
      </div>
    </div>
  );
}

function ScenariosPanel() {
  const [tech, setTech] = useState("Commvault");
  const [scenario, setScenario] = useState("");
  const [response, setResponse] = useState("");
  const [loading, setLoading] = useState(false);
  const [questionNum, setQuestionNum] = useState(1);

  async function generateScenario() {
    setResponse("");
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: "You are a Senior Backup Architect creating production interview scenarios. Make scenarios realistic with 2 AM on-call situations, escalations, multi-system failures. Format response clearly.",
          messages: [{ role: "user", content: `Generate a realistic production scenario #${questionNum} for a Backup Administrator interview focusing on ${tech}. Include: Scenario Description (realistic, time-pressured), Step-by-Step Investigation, Commands Used (in code blocks), Logs to Check (with paths), Root Cause, Resolution, Prevention Measures, Follow-up Interview Questions.` }]
        })
      });
      const data = await res.json();
      setScenario(data.content?.[0]?.text || "");
      setResponse("");
    } catch (e) { setScenario("Error."); }
    setLoading(false);
    setQuestionNum(n => n + 1);
  }

  async function getHint() {
    if (!scenario) return;
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          messages: [{ role: "user", content: `Give a model answer for a 5+ year experienced Backup Admin for this scenario:\n\n${scenario}` }]
        })
      });
      const data = await res.json();
      setResponse(data.content?.[0]?.text || "");
    } catch (e) { setResponse("Error."); }
    setLoading(false);
  }

  return (
    <div style={{ height: "100%", display: "flex", flexDirection: "column", gap: 16 }}>
      <div style={{ display: "flex", gap: 12, alignItems: "center", flexWrap: "wrap" }}>
        <select value={tech} onChange={e => setTech(e.target.value)} style={{
          background: "#0a0f1e", border: "1px solid #1a2540", borderRadius: 6,
          color: "#ffe03e", padding: "8px 12px", fontSize: 13, fontFamily: "'Space Mono', monospace",
        }}>
          {TECHNOLOGIES.map(t => <option key={t}>{t}</option>)}
        </select>
        <button onClick={generateScenario} style={{
          background: "#ffe03e", color: "#000", border: "none", borderRadius: 6,
          padding: "9px 20px", fontSize: 13, fontWeight: 700, cursor: "pointer",
          fontFamily: "'Space Mono', monospace",
        }}>Generate Scenario #{questionNum}</button>
        {scenario && !loading && (
          <button onClick={getHint} style={{
            background: "transparent", color: "#ffe03e", border: "1px solid #ffe03e",
            borderRadius: 6, padding: "9px 20px", fontSize: 13, cursor: "pointer",
            fontFamily: "'Space Mono', monospace",
          }}>Show Model Answer</button>
        )}
      </div>
      <div style={{ flex: 1, overflowY: "auto" }}>
        {loading && <TypingIndicator />}
        {!loading && scenario && (
          <div style={{ background: "#0d1525", border: "1px solid #1a2540", borderRadius: 8, padding: 20 }}>
            {formatResponse(scenario)}
          </div>
        )}
        {!loading && response && (
          <div style={{ background: "#0d1a10", border: "1px solid #a8ff3e", borderRadius: 8, padding: 20, marginTop: 16 }}>
            <div style={{ color: "#a8ff3e", fontSize: 12, fontWeight: 700, marginBottom: 12, fontFamily: "'Space Mono', monospace" }}>▶ MODEL ANSWER (5+ YOE)</div>
            {formatResponse(response)}
          </div>
        )}
        {!loading && !scenario && (
          <div style={{ color: "#2a4060", fontSize: 14, textAlign: "center", marginTop: 60 }}>
            Select a technology and generate a production scenario
          </div>
        )}
      </div>
    </div>
  );
}

function InterviewPanel() {
  const [messages, setMessages] = useState([]);
  const [input, setInput] = useState("");
  const [loading, setLoading] = useState(false);
  const [tech, setTech] = useState("Commvault");
  const [level, setLevel] = useState("L2");
  const [started, setStarted] = useState(false);
  const [score, setScore] = useState(null);
  const bottomRef = useRef(null);

  useEffect(() => { bottomRef.current?.scrollIntoView({ behavior: "smooth" }); }, [messages, loading]);

  async function startInterview() {
    setMessages([]);
    setScore(null);
    setStarted(true);
    setLoading(true);
    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: `You are a strict but fair Senior Backup Architect conducting a real technical interview for a ${level} Backup Administrator role. Ask ONE focused technical question about ${tech}. Do not provide the answer. Wait for the candidate's response. Start with a warm but professional greeting, then ask your first question.`,
          messages: [{ role: "user", content: "Start the interview." }]
        })
      });
      const data = await res.json();
      const text = data.content?.[0]?.text || "";
      setMessages([{ role: "interviewer", text }]);
    } catch (e) { setMessages([{ role: "interviewer", text: "Error starting interview." }]); }
    setLoading(false);
  }

  async function sendAnswer() {
    if (!input.trim() || loading) return;
    const userMsg = input.trim();
    setInput("");
    const newMessages = [...messages, { role: "candidate", text: userMsg }];
    setMessages(newMessages);
    setLoading(true);

    const history = newMessages.map(m => ({
      role: m.role === "candidate" ? "user" : "assistant",
      content: m.text
    }));

    try {
      const res = await fetch("https://api.anthropic.com/v1/messages", {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({
          model: "claude-sonnet-4-20250514",
          max_tokens: 1000,
          system: `You are a strict but fair Senior Backup Architect interviewing for a ${level} Backup Admin role (${tech} focus). 
Evaluate the candidate's answer: score it 1-10, point out what was correct, what was missing, what a real senior engineer would add. 
Then ask the next question. Format: 
**Evaluation:** [score/10 and feedback]
**Model Answer:** [what you expected to hear]
**Next Question:** [your next question]`,
          messages: history
        })
      });
      const data = await res.json();
      const text = data.content?.[0]?.text || "";
      setMessages(prev => [...prev, { role: "interviewer", text }]);

      // Extract score if present
      const scoreMatch = text.match(/(\d+)\/10/);
      if (scoreMatch) setScore(parseInt(scoreMatch[1]));
    } catch (e) { setMessages(prev => [...prev, { role: "interviewer", text: "Error." }]); }
    setLoading(false);
  }

  return (
    <div style={{ height: "100%", display: "flex", flexDirection: "column", gap: 12 }}>
      {!started ? (
        <div style={{ flex: 1, display: "flex", flexDirection: "column", alignItems: "center", justifyContent: "center", gap: 20 }}>
          <div style={{ color: "#b03eff", fontSize: 28, fontWeight: 900, fontFamily: "'Space Mono', monospace" }}>INTERVIEW MODE</div>
          <div style={{ color: "#7a9ab8", fontSize: 13 }}>Configure your session and begin</div>
          <div style={{ display: "flex", gap: 12, flexWrap: "wrap", justifyContent: "center" }}>
            <select value={tech} onChange={e => setTech(e.target.value)} style={{
              background: "#0a0f1e", border: "1px solid #b03eff", borderRadius: 6,
              color: "#b03eff", padding: "10px 16px", fontSize: 13, fontFamily: "'Space Mono', monospace",
            }}>
              {TECHNOLOGIES.map(t => <option key={t}>{t}</option>)}
            </select>
            <select value={level} onChange={e => setLevel(e.target.value)} style={{
              background: "#0a0f1e", border: "1px solid #b03eff", borderRadius: 6,
              color: "#b03eff", padding: "10px 16px", fontSize: 13, fontFamily: "'Space Mono', monospace",
            }}>
              <option>L1</option><option>L2</option><option>L3</option>
            </select>
          </div>
          <button onClick={startInterview} style={{
            background: "#b03eff", color: "#fff", border: "none", borderRadius: 8,
            padding: "14px 40px", fontSize: 15, fontWeight: 700, cursor: "pointer",
            fontFamily: "'Space Mono', monospace", letterSpacing: 1,
          }}>START INTERVIEW</button>
        </div>
      ) : (
        <>
          <div style={{ display: "flex", gap: 12, alignItems: "center" }}>
            <div style={{ fontSize: 12, color: "#7a9ab8", fontFamily: "'Space Mono', monospace" }}>
              {tech} · {level} · {messages.filter(m => m.role === "candidate").length} answered
            </div>
            {score !== null && (
              <div style={{
                background: score >= 7 ? "#0d1a0d" : score >= 4 ? "#1a150d" : "#1a0d0d",
                border: `1px solid ${score >= 7 ? "#a8ff3e" : score >= 4 ? "#ffe03e" : "#ff6b35"}`,
                borderRadius: 6, padding: "4px 12px", fontSize: 12, fontWeight: 700,
                color: score >= 7 ? "#a8ff3e" : score >= 4 ? "#ffe03e" : "#ff6b35",
                fontFamily: "'Space Mono', monospace",
              }}>Last: {score}/10</div>
            )}
            <button onClick={() => setStarted(false)} style={{
              marginLeft: "auto", background: "transparent", color: "#4a6080",
              border: "1px solid #1a2540", borderRadius: 6, padding: "4px 12px",
              fontSize: 12, cursor: "pointer",
            }}>End Session</button>
          </div>
          <div style={{ flex: 1, overflowY: "auto", display: "flex", flexDirection: "column", gap: 12 }}>
            {messages.map((m, i) => (
              <div key={i} style={{
                alignSelf: m.role === "candidate" ? "flex-end" : "flex-start",
                maxWidth: "85%",
              }}>
                <div style={{
                  fontSize: 10, color: "#4a6080", marginBottom: 4,
                  fontFamily: "'Space Mono', monospace", textAlign: m.role === "candidate" ? "right" : "left",
                }}>
                  {m.role === "candidate" ? "YOU" : "INTERVIEWER"}
                </div>
                <div style={{
                  background: m.role === "candidate" ? "#0d1525" : "#14091f",
                  border: `1px solid ${m.role === "candidate" ? "#00d4ff" : "#b03eff"}`,
                  borderRadius: 8, padding: "12px 16px",
                }}>
                  {formatResponse(m.text)}
                </div>
              </div>
            ))}
            {loading && (
              <div style={{ alignSelf: "flex-start", background: "#14091f", border: "1px solid #b03eff", borderRadius: 8 }}>
                <TypingIndicator />
              </div>
            )}
            <div ref={bottomRef} />
          </div>
          <div style={{ display: "flex", gap: 10 }}>
            <textarea
              value={input}
              onChange={e => setInput(e.target.value)}
              onKeyDown={e => { if (e.key === "Enter" && !e.shiftKey) { e.preventDefault(); sendAnswer(); } }}
              placeholder="Type your answer... (Enter to send, Shift+Enter for new line)"
              rows={3}
              style={{
                flex: 1, background: "#0a0f1e", border: "1px solid #1a2540",
                borderRadius: 8, padding: "10px 14px", color: "#c8d8e8",
                fontSize: 13, resize: "none", fontFamily: "'Space Mono', monospace",
                outline: "none",
              }}
            />
            <button onClick={sendAnswer} disabled={loading || !input.trim()} style={{
              background: loading ? "#1a2540" : "#b03eff", color: "#fff",
              border: "none", borderRadius: 8, padding: "0 20px", cursor: loading ? "default" : "pointer",
              fontWeight: 700, fontSize: 14, fontFamily: "'Space Mono', monospace",
            }}>SEND</button>
          </div>
        </>
      )}
    </div>
  );
}

// ─── MAIN APP ─────────────────────────────────────────────────────────────────

export default function App() {
  const [activeSection, setActiveSection] = useState("operational");

  const panels = {
    operational: OperationalPanel,
    troubleshooting: TroubleshootingPanel,
    commands: CommandsPanel,
    implementation: ImplementationPanel,
    scenarios: ScenariosPanel,
    interview: InterviewPanel,
  };

  const ActivePanel = panels[activeSection];

  return (
    <>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;700;900&display=swap');
        * { box-sizing: border-box; }
        body { margin: 0; }
        @keyframes bounce { 0%,80%,100%{transform:scale(0)} 40%{transform:scale(1)} }
        @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:0.4} }
        ::-webkit-scrollbar { width: 6px; height: 6px; }
        ::-webkit-scrollbar-track { background: #080c16; }
        ::-webkit-scrollbar-thumb { background: #1a2540; border-radius: 3px; }
        ::-webkit-scrollbar-thumb:hover { background: #2a3560; }
        textarea:focus { border-color: #b03eff !important; }
        select { cursor: pointer; }
      `}</style>
      <div style={{
        minHeight: "100vh", background: "#060a14",
        fontFamily: "'Syne', sans-serif", display: "flex", flexDirection: "column",
      }}>
        {/* Header */}
        <div style={{
          borderBottom: "1px solid #0f1a2e", padding: "16px 24px",
          display: "flex", alignItems: "center", gap: 20, flexWrap: "wrap",
        }}>
          <div>
            <div style={{
              fontSize: 18, fontWeight: 900, color: "#fff", letterSpacing: -0.5,
              fontFamily: "'Space Mono', monospace",
            }}>
              <span style={{ color: "#00d4ff" }}>BACKUP</span>
              <span style={{ color: "#4a6080" }}>::</span>
              <span style={{ color: "#ff6b35" }}>ADMIN</span>
            </div>
            <div style={{ fontSize: 10, color: "#2a4060", letterSpacing: 3, textTransform: "uppercase" }}>
              Interview Prep Platform · AI-Powered
            </div>
          </div>
          <div style={{ display: "flex", gap: 8, flexWrap: "wrap", marginLeft: "auto" }}>
            {SECTIONS.map(s => (
              <button key={s.id} onClick={() => setActiveSection(s.id)} style={{
                background: activeSection === s.id ? s.color + "15" : "transparent",
                border: `1px solid ${activeSection === s.id ? s.color : "#1a2540"}`,
                color: activeSection === s.id ? s.color : "#4a6080",
                borderRadius: 6, padding: "7px 14px", fontSize: 12,
                cursor: "pointer", fontFamily: "'Space Mono', monospace",
                fontWeight: activeSection === s.id ? 700 : 400,
                transition: "all 0.2s",
              }}>
                {s.icon} {s.label}
              </button>
            ))}
          </div>
        </div>

        {/* Section title bar */}
        <div style={{
          padding: "10px 24px", background: "#080c16", borderBottom: "1px solid #0f1a2e",
          display: "flex", alignItems: "center", gap: 12,
        }}>
          {(() => { const s = SECTIONS.find(x => x.id === activeSection); return <>
            <div style={{ width: 6, height: 6, borderRadius: "50%", background: s.color, animation: "pulse 2s infinite" }} />
            <span style={{ color: s.color, fontSize: 12, fontWeight: 700, fontFamily: "'Space Mono', monospace", letterSpacing: 2 }}>
              {s.label.toUpperCase()}
            </span>
            <span style={{ color: "#2a4060", fontSize: 11 }}>
              {activeSection === "operational" && "10 daily tasks with production procedures"}
              {activeSection === "troubleshooting" && "20 real-world issues with RCA & resolution"}
              {activeSection === "commands" && "Complete command reference by category"}
              {activeSection === "implementation" && "13 implementation guides with rollback plans"}
              {activeSection === "scenarios" && "Infinite AI-generated production scenarios"}
              {activeSection === "interview" && "Live AI interviewer with real-time evaluation"}
            </span>
          </>; })()}
        </div>

        {/* Main content */}
        <div style={{ flex: 1, padding: 24, overflow: "hidden", display: "flex", flexDirection: "column" }}>
          <div style={{
            flex: 1, background: "#080c16", border: "1px solid #0f1a2e", borderRadius: 12,
            padding: 20, overflow: "hidden", display: "flex", flexDirection: "column",
          }}>
            <ActivePanel />
          </div>
        </div>

        {/* Footer */}
        <div style={{
          borderTop: "1px solid #0f1a2e", padding: "8px 24px",
          display: "flex", gap: 16, alignItems: "center",
        }}>
          {TECHNOLOGIES.slice(0, 7).map(t => (
            <span key={t} style={{ fontSize: 10, color: "#1a3050", fontFamily: "'Space Mono', monospace" }}>{t}</span>
          ))}
        </div>
      </div>
    </>
  );
}
