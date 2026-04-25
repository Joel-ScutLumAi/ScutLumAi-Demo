import { useState } from "react";
import Head from "next/head";

const SAMPLES = [
  {
    id: 1,
    label: "Unhedged future claim",
    sentence: "The company will definitely achieve record revenues next quarter.",
    confidence_signals: ["Unhedged future claim", "Commitment amplifier"],
    support_signals: [],
    modifiers: ["Commitment amplifier"],
    structural_state: "unaccompanied",
    state_label: "Unaccompanied",
    state_type: "danger",
    description: "A forward-looking assertion expressed with absolute certainty. No evidentiary support signal is present within this structural unit."
  },
  {
    id: 2,
    label: "Fully accompanied",
    sentence: "Revenue increased 34% to $2.1 billion, as reported in our Q3 10-Q filing with the SEC.",
    confidence_signals: ["Present state assertion"],
    support_signals: ["Audited figure", "Regulatory filing reference"],
    modifiers: [],
    structural_state: "fully_accompanied",
    state_label: "Fully accompanied",
    state_type: "success",
    description: "A quantitative performance claim accompanied by both a verified figure and a named regulatory filing. Structural correspondence: present."
  },
  {
    id: 3,
    label: "Cascading unaccompanied",
    sentence: "Our revolutionary platform is the undisputed market leader, driving exceptional growth across every segment globally.",
    confidence_signals: ["Superlative market position claim", "Momentum assertion", "Characterization claim"],
    support_signals: [],
    modifiers: ["Scope inflation marker", "Commitment amplifier"],
    structural_state: "cascading_unaccompanied",
    state_label: "Cascading unaccompanied",
    state_type: "danger",
    description: "Multiple compounding confidence signals — superlative positioning, directional momentum, and qualitative characterization — with no support signal present. Scope inflation detected."
  },
  {
    id: 4,
    label: "Hedged, unaccompanied",
    sentence: "Management believes growth could continue into the following fiscal year.",
    confidence_signals: ["Hedged future claim"],
    support_signals: [],
    modifiers: [],
    structural_state: "hedged_unaccompanied",
    state_label: "Hedged, unaccompanied",
    state_type: "warning",
    description: "A forward-looking claim qualified by hedging language. No evidentiary support signal is present. The hedge is structurally noted but does not constitute accompaniment."
  },
  {
    id: 5,
    label: "Stakeholder universalization",
    sentence: "All stakeholders will benefit from our industry-leading performance.",
    confidence_signals: ["Characterization claim", "Unhedged future claim"],
    support_signals: [],
    modifiers: ["Stakeholder universalization", "Scope inflation marker"],
    structural_state: "unaccompanied",
    state_label: "Unaccompanied",
    state_type: "danger",
    description: "A universal beneficiary claim combined with a performance characterization. Stakeholder universalization modifier detected — scope of claim exceeds any available evidentiary basis within this unit."
  }
];

const STATE_COLORS = {
  danger: { bg: "#FEF2F2", text: "#991B1B", border: "#FECACA" },
  success: { bg: "#F0FDF4", text: "#166534", border: "#BBF7D0" },
  warning: { bg: "#FFFBEB", text: "#92400E", border: "#FDE68A" }
};

const BADGE_STYLES = {
  confidence: { bg: "#FFFBEB", text: "#92400E", border: "#FDE68A" },
  support: { bg: "#EFF6FF", text: "#1E40AF", border: "#BFDBFE" },
  modifier: { bg: "#F9FAFB", text: "#374151", border: "#E5E7EB" }
};

function Badge({ label, type }) {
  const s = BADGE_STYLES[type];
  return (
    <span style={{
      background: s.bg, color: s.text, border: `0.5px solid ${s.border}`,
      fontSize: 11, padding: "2px 8px", borderRadius: 6,
      fontFamily: "monospace", display: "inline-block",
      marginRight: 4, marginBottom: 4
    }}>
      {label}
    </span>
  );
}

export default function ScutLumAi() {
  const [selected, setSelected] = useState(null);

  const unit = selected !== null ? SAMPLES[selected] : null;
  const stateColor = unit ? STATE_COLORS[unit.state_type] : null;

  return (
    <>
      <Head>
        <title>ScutLumAi — Structural Signal Demo</title>
        <meta name="description" content="ScutLumAi is a structural signal assessment infrastructure for financial publishing. This is a concept prototype." />
        <meta property="og:title" content="ScutLumAi — Structural Signal Demo" />
        <meta property="og:description" content="Structural signal detection for financial copy. Not an AI writing tool. Not a risk rater. A structural mirror." />
        <link rel="preconnect" href="https://fonts.googleapis.com" />
        <link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500&family=IBM+Plex+Sans:wght@400;500&display=swap" rel="stylesheet" />
      </Head>

      <div style={{ minHeight: "100vh", background: "#FAFAF9", fontFamily: "'IBM Plex Sans', sans-serif" }}>

        {/* Header */}
        <div style={{ borderBottom: "0.5px solid #E5E5E3", background: "#FFFFFF", padding: "18px 0" }}>
          <div style={{ maxWidth: 760, margin: "0 auto", padding: "0 24px", display: "flex", alignItems: "center", justifyContent: "space-between" }}>
            <div style={{ display: "flex", alignItems: "center", gap: 12 }}>
              <span style={{ fontSize: 17, fontWeight: 500, letterSpacing: "-0.02em", color: "#111110" }}>ScutLumAi</span>
              <span style={{ fontSize: 10, fontFamily: "'IBM Plex Mono', monospace", color: "#6B7280", background: "#F3F4F6", padding: "2px 8px", borderRadius: 6, border: "0.5px solid #E5E7EB" }}>
                CONCEPT PROTOTYPE · MVP-1.0
              </span>
            </div>
            <span style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF" }}>
              Constitutional Signal Infrastructure
            </span>
          </div>
        </div>

        <div style={{ maxWidth: 760, margin: "0 auto", padding: "40px 24px" }}>

          {/* Mandate */}
          <div style={{ background: "#FFFFFF", border: "0.5px solid #E5E5E3", borderRadius: 12, padding: "20px 24px", marginBottom: 32 }}>
            <p style={{ fontSize: 13, lineHeight: 1.75, color: "#374151", margin: 0 }}>
              This is not an AI writing tool. It does not assess quality, detect misinformation, or recommend edits.
              It detects structural relationships between certainty and evidentiary support — and describes what it finds.{" "}
              <strong style={{ fontWeight: 500, color: "#111110" }}>Nothing more.</strong>
            </p>
          </div>

          {/* Sample selector */}
          <div style={{ marginBottom: 28 }}>
            <p style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#6B7280", margin: "0 0 12px 0", letterSpacing: "0.06em" }}>
              SELECT A STRUCTURAL UNIT
            </p>
            <div style={{ display: "flex", flexDirection: "column", gap: 8 }}>
              {SAMPLES.map((s, i) => (
                <button
                  key={s.id}
                  onClick={() => setSelected(i)}
                  style={{
                    textAlign: "left", background: selected === i ? "#FFFFFF" : "transparent",
                    border: `0.5px solid ${selected === i ? "#111110" : "#E5E5E3"}`,
                    borderRadius: 10, padding: "12px 16px", cursor: "pointer",
                    transition: "all 0.15s ease"
                  }}
                >
                  <div style={{ display: "flex", alignItems: "flex-start", gap: 12 }}>
                    <span style={{
                      fontSize: 10, fontFamily: "'IBM Plex Mono', monospace",
                      color: selected === i ? "#111110" : "#9CA3AF",
                      minWidth: 20, marginTop: 1
                    }}>
                      {String(i + 1).padStart(2, "0")}
                    </span>
                    <div>
                      <p style={{ fontSize: 13, color: "#111110", margin: "0 0 3px 0", fontWeight: selected === i ? 500 : 400 }}>
                        {s.sentence}
                      </p>
                      <p style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: 0 }}>
                        {s.label}
                      </p>
                    </div>
                  </div>
                </button>
              ))}
            </div>
          </div>

          {/* Output panel */}
          {unit && stateColor && (
            <div style={{ background: "#FFFFFF", border: "0.5px solid #E5E5E3", borderRadius: 12, overflow: "hidden" }}>

              <div style={{ padding: "16px 24px", borderBottom: "0.5px solid #E5E5E3", background: "#FAFAF9" }}>
                <p style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#6B7280", margin: "0 0 4px 0", letterSpacing: "0.06em" }}>
                  STRUCTURAL UNIT — ENGINE OUTPUT
                </p>
                <p style={{ fontSize: 14, lineHeight: 1.7, color: "#111110", margin: 0, borderLeft: "2px solid #D1D5DB", paddingLeft: 12 }}>
                  {unit.sentence}
                </p>
              </div>

              <div style={{ padding: "20px 24px" }}>

                <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 20, marginBottom: 20 }}>
                  <div>
                    <p style={{ fontSize: 10, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: "0 0 8px 0", letterSpacing: "0.06em" }}>
                      CONFIDENCE SIGNALS
                    </p>
                    {unit.confidence_signals.length
                      ? unit.confidence_signals.map(s => <Badge key={s} label={s} type="confidence" />)
                      : <span style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#D1D5DB" }}>none detected</span>
                    }
                  </div>
                  <div>
                    <p style={{ fontSize: 10, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: "0 0 8px 0", letterSpacing: "0.06em" }}>
                      SUPPORT SIGNALS
                    </p>
                    {unit.support_signals.length
                      ? unit.support_signals.map(s => <Badge key={s} label={s} type="support" />)
                      : <span style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#D1D5DB" }}>none detected</span>
                    }
                  </div>
                </div>

                {unit.modifiers.length > 0 && (
                  <div style={{ marginBottom: 20 }}>
                    <p style={{ fontSize: 10, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: "0 0 8px 0", letterSpacing: "0.06em" }}>
                      SIGNAL MODIFIERS
                    </p>
                    {unit.modifiers.map(m => <Badge key={m} label={m} type="modifier" />)}
                  </div>
                )}

                <div style={{ display: "flex", alignItems: "flex-start", gap: 12, padding: "14px 16px", background: stateColor.bg, border: `0.5px solid ${stateColor.border}`, borderRadius: 10 }}>
                  <div style={{ flex: 1 }}>
                    <p style={{ fontSize: 10, fontFamily: "'IBM Plex Mono', monospace", color: stateColor.text, margin: "0 0 4px 0", letterSpacing: "0.06em", opacity: 0.7 }}>
                      STRUCTURAL STATE
                    </p>
                    <p style={{ fontSize: 13, fontWeight: 500, color: stateColor.text, margin: "0 0 6px 0", fontFamily: "'IBM Plex Mono', monospace" }}>
                      {unit.state_label}
                    </p>
                    <p style={{ fontSize: 12, color: stateColor.text, margin: 0, lineHeight: 1.65, opacity: 0.85 }}>
                      {unit.description}
                    </p>
                  </div>
                </div>

              </div>

              <div style={{ padding: "12px 24px", borderTop: "0.5px solid #E5E5E3", background: "#FAFAF9" }}>
                <p style={{ fontSize: 10, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: 0, lineHeight: 1.6 }}>
                  Output is structural description only. No judgment, risk rating, or recommendation is expressed or implied.
                  Signal interpretation remains with the human editor. · engine MVP-1.0 · taxonomy DEMO-SUBSET-1
                </p>
              </div>

            </div>
          )}

          {!unit && (
            <div style={{ border: "0.5px dashed #E5E5E3", borderRadius: 12, padding: "32px 24px", textAlign: "center" }}>
              <p style={{ fontSize: 12, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: 0 }}>
                Select a structural unit above to view engine output
              </p>
            </div>
          )}

          {/* Footer */}
          <div style={{ marginTop: 48, paddingTop: 24, borderTop: "0.5px solid #E5E5E3" }}>
            <p style={{ fontSize: 11, fontFamily: "'IBM Plex Mono', monospace", color: "#9CA3AF", margin: 0, lineHeight: 1.8 }}>
              ScutLumAi is a structural signal assessment infrastructure for financial publishing workflows.<br />
              This prototype demonstrates the constitutional engine&apos;s signal detection on a curated subset of the full taxonomy.<br />
              The engine does not determine truth. It does not assign risk ratings. It does not produce probabilistic conclusions.
            </p>
          </div>

        </div>
      </div>
    </>
  );
}
