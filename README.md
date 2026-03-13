import { useState, useEffect } from "react";

const skills = {
  Frontend: ["HTML5", "CSS3", "JavaScript", "React", "Tailwind CSS"],
  Backend: ["Node.js", "Express.js"],
  Database: ["MongoDB"],
  Tools: ["Git", "GitHub", "VS Code", "Figma"],
};

const socials = [
  {
    name: "LinkedIn",
    url: "https://www.linkedin.com/in/rajendra-bist-169926370",
    icon: (
      <svg viewBox="0 0 24 24" fill="currentColor" className="w-5 h-5">
        <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" />
      </svg>
    ),
    color: "#0A66C2",
  },
  {
    name: "Instagram",
    url: "https://www.instagram.com/rajendrabist07",
    icon: (
      <svg viewBox="0 0 24 24" fill="currentColor" className="w-5 h-5">
        <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z" />
      </svg>
    ),
    color: "#E4405F",
  },
  {
    name: "Facebook",
    url: "https://www.facebook.com/share/1FXc1WLiqS/",
    icon: (
      <svg viewBox="0 0 24 24" fill="currentColor" className="w-5 h-5">
        <path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z" />
      </svg>
    ),
    color: "#1877F2",
  },
];

const stats = [
  { label: "Projects Built", value: "10+" },
  { label: "Technologies", value: "8+" },
  { label: "Commits", value: "500+" },
  { label: "Coffee Cups", value: "∞" },
];

function TypeWriter({ texts }) {
  const [displayed, setDisplayed] = useState("");
  const [textIdx, setTextIdx] = useState(0);
  const [charIdx, setCharIdx] = useState(0);
  const [deleting, setDeleting] = useState(false);

  useEffect(() => {
    const current = texts[textIdx];
    const timeout = setTimeout(
      () => {
        if (!deleting) {
          setDisplayed(current.slice(0, charIdx + 1));
          if (charIdx + 1 === current.length) {
            setTimeout(() => setDeleting(true), 1500);
          } else {
            setCharIdx((c) => c + 1);
          }
        } else {
          setDisplayed(current.slice(0, charIdx - 1));
          if (charIdx - 1 === 0) {
            setDeleting(false);
            setTextIdx((i) => (i + 1) % texts.length);
            setCharIdx(0);
          } else {
            setCharIdx((c) => c - 1);
          }
        }
      },
      deleting ? 40 : 80
    );
    return () => clearTimeout(timeout);
  }, [charIdx, deleting, textIdx, texts]);

  return (
    <span>
      {displayed}
      <span className="animate-pulse">|</span>
    </span>
  );
}

export default function App() {
  const [activeSkill, setActiveSkill] = useState("Frontend");
  const [mounted, setMounted] = useState(false);

  useEffect(() => {
    setMounted(true);
  }, []);

  return (
    <div
      style={{
        minHeight: "100vh",
        background: "#0a0a0f",
        fontFamily: "'Sora', 'DM Sans', sans-serif",
        color: "#e8e8f0",
        overflowX: "hidden",
      }}
    >
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Sora:wght@300;400;500;600;700;800&family=Space+Mono:wght@400;700&display=swap');
        
        * { box-sizing: border-box; margin: 0; padding: 0; }
        
        .glow-text {
          background: linear-gradient(135deg, #7DF9FF 0%, #00d4ff 40%, #a78bfa 80%);
          -webkit-background-clip: text;
          -webkit-text-fill-color: transparent;
          background-clip: text;
        }
        
        .card {
          background: rgba(255,255,255,0.03);
          border: 1px solid rgba(255,255,255,0.08);
          border-radius: 20px;
          backdrop-filter: blur(10px);
          transition: all 0.3s ease;
        }
        
        .card:hover {
          border-color: rgba(125, 249, 255, 0.25);
          background: rgba(125, 249, 255, 0.04);
          transform: translateY(-2px);
        }
        
        .skill-tag {
          display: inline-flex;
          align-items: center;
          padding: 6px 14px;
          border-radius: 100px;
          font-size: 13px;
          font-weight: 500;
          border: 1px solid rgba(125,249,255,0.2);
          background: rgba(125,249,255,0.06);
          color: #7df9ff;
          transition: all 0.2s;
          cursor: default;
          letter-spacing: 0.02em;
        }
        
        .skill-tag:hover {
          background: rgba(125,249,255,0.15);
          border-color: rgba(125,249,255,0.5);
          transform: scale(1.05);
        }
        
        .tab-btn {
          padding: 8px 18px;
          border-radius: 100px;
          font-size: 13px;
          font-weight: 500;
          border: 1px solid transparent;
          cursor: pointer;
          transition: all 0.2s;
          font-family: 'Sora', sans-serif;
          letter-spacing: 0.02em;
        }
        
        .tab-btn.active {
          background: linear-gradient(135deg, #7df9ff22, #a78bfa22);
          border-color: rgba(125,249,255,0.4);
          color: #7df9ff;
        }
        
        .tab-btn.inactive {
          background: transparent;
          color: #888;
        }
        
        .tab-btn.inactive:hover {
          color: #ccc;
          border-color: rgba(255,255,255,0.15);
        }
        
        .social-btn {
          display: flex;
          align-items: center;
          gap: 10px;
          padding: 12px 22px;
          border-radius: 14px;
          font-size: 14px;
          font-weight: 500;
          border: 1px solid rgba(255,255,255,0.1);
          background: rgba(255,255,255,0.04);
          color: #ccc;
          text-decoration: none;
          transition: all 0.25s;
          font-family: 'Sora', sans-serif;
        }
        
        .social-btn:hover {
          border-color: rgba(255,255,255,0.25);
          background: rgba(255,255,255,0.08);
          color: #fff;
          transform: translateX(3px);
        }
        
        .stat-card {
          text-align: center;
          padding: 20px;
          border-radius: 18px;
          background: rgba(255,255,255,0.03);
          border: 1px solid rgba(255,255,255,0.07);
          transition: all 0.3s;
        }
        
        .stat-card:hover {
          background: rgba(125,249,255,0.05);
          border-color: rgba(125,249,255,0.2);
        }
        
        .noise {
          position: fixed;
          top: 0; left: 0;
          width: 100%; height: 100%;
          pointer-events: none;
          opacity: 0.025;
          z-index: 0;
          background-image: url("data:image/svg+xml,%3Csvg viewBox='0 0 200 200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)'/%3E%3C/svg%3E");
          background-size: 200px;
        }
        
        .orb {
          position: fixed;
          border-radius: 50%;
          pointer-events: none;
          filter: blur(80px);
          opacity: 0.12;
        }

        .fade-in {
          animation: fadeUp 0.7s ease forwards;
          opacity: 0;
        }
        
        @keyframes fadeUp {
          from { opacity: 0; transform: translateY(20px); }
          to { opacity: 1; transform: translateY(0); }
        }
        
        .mono { font-family: 'Space Mono', monospace; }
        
        .divider {
          height: 1px;
          background: linear-gradient(90deg, transparent, rgba(255,255,255,0.08), transparent);
          margin: 32px 0;
        }

        .avatar-ring {
          background: linear-gradient(135deg, #7df9ff, #a78bfa, #7df9ff);
          padding: 3px;
          border-radius: 50%;
          display: inline-block;
        }

        .avatar-inner {
          background: #0a0a0f;
          border-radius: 50%;
          padding: 4px;
        }

        .pulse-dot {
          width: 10px;
          height: 10px;
          background: #22c55e;
          border-radius: 50%;
          animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
          0%, 100% { opacity: 1; transform: scale(1); }
          50% { opacity: 0.5; transform: scale(1.3); }
        }

        .quote-block {
          border-left: 2px solid #7df9ff44;
          padding-left: 20px;
          font-style: italic;
          color: #aaa;
          line-height: 1.8;
        }
      `}</style>

      {/* Background orbs */}
      <div
        className="orb"
        style={{
          width: 600,
          height: 600,
          background: "#7df9ff",
          top: -200,
          right: -200,
        }}
      />
      <div
        className="orb"
        style={{
          width: 500,
          height: 500,
          background: "#a78bfa",
          bottom: -100,
          left: -150,
        }}
      />
      <div className="noise" />

      {/* Content */}
      <div
        style={{
          maxWidth: 760,
          margin: "0 auto",
          padding: "60px 24px 80px",
          position: "relative",
          zIndex: 1,
        }}
      >
        {/* Header */}
        <div
          className="fade-in"
          style={{ animationDelay: "0s", textAlign: "center", marginBottom: 56 }}
        >
          {/* Avatar */}
          <div
            style={{
              display: "flex",
              justifyContent: "center",
              marginBottom: 24,
            }}
          >
            <div className="avatar-ring">
              <div className="avatar-inner">
                <div
                  style={{
                    width: 88,
                    height: 88,
                    borderRadius: "50%",
                    background: "linear-gradient(135deg, #1a1a2e, #16213e)",
                    display: "flex",
                    alignItems: "center",
                    justifyContent: "center",
                    fontSize: 36,
                  }}
                >
                  🧑‍💻
                </div>
              </div>
            </div>
          </div>

          {/* Status */}
          <div
            style={{
              display: "inline-flex",
              alignItems: "center",
              gap: 8,
              padding: "6px 16px",
              borderRadius: 100,
              background: "rgba(34,197,94,0.1)",
              border: "1px solid rgba(34,197,94,0.25)",
              marginBottom: 20,
            }}
          >
            <div className="pulse-dot" />
            <span
              style={{ fontSize: 12, color: "#22c55e", fontWeight: 500, letterSpacing: "0.05em" }}
            >
              AVAILABLE FOR OPPORTUNITIES
            </span>
          </div>

          <h1
            style={{
              fontSize: "clamp(36px, 7vw, 58px)",
              fontWeight: 800,
              letterSpacing: "-0.03em",
              lineHeight: 1.1,
              marginBottom: 16,
            }}
          >
            Rajendra{" "}
            <span className="glow-text">Bist</span>
          </h1>

          <div
            className="mono"
            style={{ fontSize: 16, color: "#888", marginBottom: 8, letterSpacing: "0.02em" }}
          >
            ~/
            <span style={{ color: "#7df9ff" }}>
              <TypeWriter
                texts={[
                  "full-stack-dev",
                  "mern-specialist",
                  "ui-architect",
                  "problem-solver",
                ]}
              />
            </span>
          </div>

          <p
            style={{
              fontSize: 15,
              color: "#666",
              maxWidth: 480,
              margin: "16px auto 0",
              lineHeight: 1.7,
            }}
          >
            Crafting performant, scalable web applications with clean architecture.
            Turning complex ideas into elegant, production-ready solutions.
          </p>
        </div>

        {/* Stats */}
        <div
          className="fade-in"
          style={{
            animationDelay: "0.15s",
            display: "grid",
            gridTemplateColumns: "repeat(4, 1fr)",
            gap: 12,
            marginBottom: 40,
          }}
        >
          {stats.map((s) => (
            <div key={s.label} className="stat-card">
              <div
                className="mono glow-text"
                style={{ fontSize: 26, fontWeight: 700, marginBottom: 4 }}
              >
                {s.value}
              </div>
              <div style={{ fontSize: 11, color: "#555", letterSpacing: "0.06em", textTransform: "uppercase" }}>
                {s.label}
              </div>
            </div>
          ))}
        </div>

        {/* About */}
        <div
          className="fade-in card"
          style={{ animationDelay: "0.2s", padding: 32, marginBottom: 24 }}
        >
          <div
            style={{
              display: "flex",
              alignItems: "center",
              gap: 10,
              marginBottom: 20,
            }}
          >
            <span style={{ fontSize: 18 }}>🚀</span>
            <h2
              style={{ fontSize: 16, fontWeight: 700, letterSpacing: "0.05em", textTransform: "uppercase", color: "#7df9ff" }}
            >
              About Me
            </h2>
          </div>
          <div style={{ display: "flex", flexDirection: "column", gap: 12 }}>
            {[
              { icon: "🔭", text: "Building real-world full-stack applications end-to-end" },
              { icon: "🌱", text: "Mastering the JavaScript ecosystem — React, Node.js, and beyond" },
              { icon: "🧠", text: "Passionate about clean architecture and scalable system design" },
              { icon: "🎯", text: "Goal: shipping production-ready products that solve real problems" },
            ].map((item) => (
              <div
                key={item.text}
                style={{ display: "flex", alignItems: "flex-start", gap: 12 }}
              >
                <span style={{ fontSize: 16, marginTop: 1 }}>{item.icon}</span>
                <span style={{ fontSize: 14, color: "#aaa", lineHeight: 1.6 }}>{item.text}</span>
              </div>
            ))}
          </div>
        </div>

        {/* Skills */}
        <div
          className="fade-in card"
          style={{ animationDelay: "0.3s", padding: 32, marginBottom: 24 }}
        >
          <div
            style={{
              display: "flex",
              alignItems: "center",
              gap: 10,
              marginBottom: 20,
            }}
          >
            <span style={{ fontSize: 18 }}>🛠️</span>
            <h2
              style={{ fontSize: 16, fontWeight: 700, letterSpacing: "0.05em", textTransform: "uppercase", color: "#7df9ff" }}
            >
              Tech Stack
            </h2>
          </div>

          {/* Tabs */}
          <div style={{ display: "flex", gap: 8, flexWrap: "wrap", marginBottom: 20 }}>
            {Object.keys(skills).map((cat) => (
              <button
                key={cat}
                onClick={() => setActiveSkill(cat)}
                className={`tab-btn ${activeSkill === cat ? "active" : "inactive"}`}
              >
                {cat}
              </button>
            ))}
          </div>

          {/* Tags */}
          <div style={{ display: "flex", flexWrap: "wrap", gap: 8 }}>
            {skills[activeSkill].map((skill) => (
              <span key={skill} className="skill-tag">
                {skill}
              </span>
            ))}
          </div>
        </div>

        {/* Connect */}
        <div
          className="fade-in card"
          style={{ animationDelay: "0.4s", padding: 32, marginBottom: 24 }}
        >
          <div
            style={{
              display: "flex",
              alignItems: "center",
              gap: 10,
              marginBottom: 20,
            }}
          >
            <span style={{ fontSize: 18 }}>🌐</span>
            <h2
              style={{ fontSize: 16, fontWeight: 700, letterSpacing: "0.05em", textTransform: "uppercase", color: "#7df9ff" }}
            >
              Connect With Me
            </h2>
          </div>
          <div style={{ display: "flex", flexDirection: "column", gap: 10 }}>
            {socials.map((s) => (
              <a
                key={s.name}
                href={s.url}
                target="_blank"
                rel="noreferrer"
                className="social-btn"
              >
                <span style={{ color: s.color }}>{s.icon}</span>
                <span>{s.name}</span>
                <span style={{ marginLeft: "auto", fontSize: 12, color: "#555" }}>↗</span>
              </a>
            ))}
          </div>
        </div>

        {/* Philosophy */}
        <div
          className="fade-in card"
          style={{ animationDelay: "0.5s", padding: 32, marginBottom: 40 }}
        >
          <div
            style={{
              display: "flex",
              alignItems: "center",
              gap: 10,
              marginBottom: 20,
            }}
          >
            <span style={{ fontSize: 18 }}>💭</span>
            <h2
              style={{ fontSize: 16, fontWeight: 700, letterSpacing: "0.05em", textTransform: "uppercase", color: "#7df9ff" }}
            >
              Philosophy
            </h2>
          </div>
          <div className="quote-block">
            <p style={{ marginBottom: 8 }}>
              Code is not just written —
            </p>
            <p style={{ marginBottom: 8 }}>
              it is <em style={{ color: "#7df9ff" }}>designed</em>, <em style={{ color: "#a78bfa" }}>structured</em>, and <em style={{ color: "#f472b6" }}>evolved</em>.
            </p>
          </div>
        </div>

        {/* Footer */}
        <div
          className="fade-in"
          style={{ animationDelay: "0.6s", textAlign: "center" }}
        >
          <div className="divider" />
          <div
            className="mono"
            style={{ fontSize: 13, color: "#444", letterSpacing: "0.08em" }}
          >
            ⭐ BUILDING · LEARNING · IMPROVING · EVERY DAY
          </div>
        </div>
      </div>
    </div>
  );
}
