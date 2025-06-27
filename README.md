import React, { useState } from "react";

export default function SafeSpaceApp() {
  const [tab, setTab] = useState("report");
  const [report, setReport] = useState("");
  const [supportMessage, setSupportMessage] = useState("");

  const containerStyle = {
    padding: "20px",
    maxWidth: "600px",
    margin: "0 auto",
    fontFamily: "Arial, sans-serif",
  };
  const headerStyle = {
    textAlign: "center",
    fontSize: "28px",
    fontWeight: "bold",
  };
  const taglineStyle = {
    textAlign: "center",
    fontSize: "14px",
    color: "gray",
  };
  const tabBarStyle = {
    display: "flex",
    justifyContent: "center",
    marginTop: "20px",
    gap: "10px",
  };
  const activeTabStyle = {
    padding: "10px 20px",
    border: "none",
    backgroundColor: "#4f46e5",
    color: "white",
    cursor: "pointer",
  };
  const inactiveTabStyle = {
    padding: "10px 20px",
    border: "1px solid #ccc",
    backgroundColor: "white",
    color: "black",
    cursor: "pointer",
  };
  const cardStyle = {
    border: "1px solid #ddd",
    padding: "20px",
    borderRadius: "10px",
    marginTop: "20px",
  };
  const textareaStyle = {
    width: "100%",
    height: "100px",
    marginBottom: "10px",
    padding: "10px",
    fontSize: "14px",
    borderRadius: "4px",
    border: "1px solid #ccc",
  };
  const buttonStyle = (bgColor) => ({
    width: "100%",
    padding: "10px",
    marginTop: "10px",
    backgroundColor: bgColor,
    color: "white",
    border: "none",
    borderRadius: "4px",
    cursor: "pointer",
    fontSize: "16px",
  });

  return (
    <div style={containerStyle}>
      <h1 style={headerStyle}>SafeSpace: Anti-Bullying App</h1>
      <p style={taglineStyle}>“Speak Up. Stay Safe. You’re Not Alone.”</p>

      <div style={tabBarStyle}>
        <button
          style={tab === "report" ? activeTabStyle : inactiveTabStyle}
          onClick={() => setTab("report")}
        >
          🛡️ Report Bullying
        </button>
        <button
          style={tab === "support" ? activeTabStyle : inactiveTabStyle}
          onClick={() => setTab("support")}
        >
          🤝 Get Support
        </button>
      </div>

      {tab === "report" && (
        <div style={cardStyle}>
          <textarea
            placeholder="Describe the incident anonymously..."
            value={report}
            onChange={(e) => setReport(e.target.value)}
            style={textareaStyle}
          />
          <input type="file" multiple style={{ marginBottom: "10px" }} />
          <button style={buttonStyle("#4f46e5")}>📤 Submit Report</button>
          <button style={buttonStyle("#dc2626")}>
            🚨 Real-Time Emergency Help
          </button>
        </div>
      )}

      {tab === "support" && (
        <div style={cardStyle}>
          <textarea
            placeholder="Message a trained peer supporter anonymously..."
            value={supportMessage}
            onChange={(e) => setSupportMessage(e.target.value)}
            style={textareaStyle}
          />
          <button style={buttonStyle("#4f46e5")}>🤝 Send Message</button>
          <button style={buttonStyle("#6b7280")}>
            📞 Book Counsellor Session
          </button>
          <button style={buttonStyle("#3b82f6")}>
            📚 View Educational Resources
          </button>
          <button style={buttonStyle("#10b981")}>📈 Track My Reports</button>
        </div>
      )}
    </div>
  );
}
