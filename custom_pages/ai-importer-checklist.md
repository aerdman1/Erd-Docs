---
title: AI Importer Checklist
fullscreen: false
hidden: false
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AI Import QA</title>
  <style>
/* ReadMe overrides */
.SuperHubCustomPage-content2y25YXtWEbiK { margin: 0 auto; max-width: 100%; padding: 0; }
header.SuperHubCustomPage-content-header,
.rm-Header_compact Header,
header.Header3zzata9F_ZPQ.rm-Header_compact.Header_collapsible3n0YXfOvb_Al.rm-Header { display: none !important; }

:root {
  --text: #1f2933;
  --muted: #64748b;
  --border: #e2e8f0;
  --sidebar-bg: #f8fafc;
  --sidebar-w: 210px;
  --topbar-h: 52px;
  --red: #dc2626;
  --green: #16a34a;
  --orange: #d97706;
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Arial, sans-serif;
  color: var(--text);
  background: #fff;
  font-size: 13px;
  line-height: 1.4;
}

/* ── Top bar ── */
.qa-topbar {
  height: var(--topbar-h);
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 0 16px;
  border-bottom: 1px solid var(--border);
  background: #fff;
  position: sticky;
  top: 0;
  z-index: 10;
}

.qa-logo {
  font-size: 14px;
  font-weight: 700;
  letter-spacing: -0.02em;
  white-space: nowrap;
  flex-shrink: 0;
}

.qa-fields {
  display: flex;
  gap: 6px;
  flex: 1;
  min-width: 0;
}

.qa-fields input {
  flex: 1;
  min-width: 80px;
  padding: 5px 9px;
  font-size: 12px;
  border: 1.5px solid var(--border);
  border-radius: 6px;
  color: var(--text);
  font-family: inherit;
  outline: none;
  background: #f8fafc;
  transition: border-color 0.15s, background 0.15s;
}
.qa-fields input:focus { border-color: #94a3b8; background: #fff; }

.qa-actions { display: flex; gap: 6px; flex-shrink: 0; }

.btn {
  padding: 5px 13px;
  font-size: 12px;
  font-weight: 600;
  border-radius: 6px;
  cursor: pointer;
  white-space: nowrap;
  font-family: inherit;
  border: 1.5px solid;
  transition: all 0.15s;
  line-height: 1.4;
}
.btn-primary  { background: #1e293b; border-color: #1e293b; color: #fff; }
.btn-primary:hover  { background: #334155; border-color: #334155; }
.btn-ghost   { background: #fff; border-color: var(--border); color: var(--text); }
.btn-ghost:hover { background: #f1f5f9; border-color: #cbd5e1; }
.btn-danger  { background: #fff; border-color: #fca5a5; color: var(--red); }
.btn-danger:hover { background: #fef2f2; }

/* ── Body layout ── */
.qa-body {
  display: flex;
  height: calc(100vh - var(--topbar-h) - 70px); /* 70px ≈ ReadMe chrome */
  overflow: hidden;
}

/* ── Sidebar ── */
.qa-sidebar {
  width: var(--sidebar-w);
  flex-shrink: 0;
  background: var(--sidebar-bg);
  border-right: 1px solid var(--border);
  display: flex;
  flex-direction: column;
  overflow-y: auto;
  padding: 8px 0;
}

.nav-group-label {
  font-size: 10px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.07em;
  color: var(--muted);
  padding: 10px 14px 4px;
}

.qa-nav-item {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 7px 14px;
  cursor: pointer;
  border-radius: 0;
  transition: background 0.1s;
  position: relative;
  user-select: none;
}
.qa-nav-item:hover { background: #f1f5f9; }
.qa-nav-item.active {
  background: #fff;
  font-weight: 600;
  box-shadow: inset 3px 0 0 #1e293b;
}

.nav-icon { font-size: 13px; flex-shrink: 0; width: 18px; text-align: center; }
.nav-label { flex: 1; font-size: 12px; }

.nav-badge {
  font-size: 10px;
  font-weight: 700;
  min-width: 18px;
  height: 18px;
  border-radius: 9px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0 5px;
}
.badge-red   { background: #fee2e2; color: var(--red); }
.badge-green { background: #dcfce7; color: var(--green); }
.badge-none  { display: none; }

/* ── Grade box in sidebar ── */
.qa-grade-box {
  margin-top: auto;
  border-top: 1px solid var(--border);
  padding: 14px;
}
.grade-label {
  font-size: 10px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.07em;
  color: var(--muted);
  margin-bottom: 4px;
}
.grade-value {
  font-size: 22px;
  font-weight: 800;
  letter-spacing: -0.02em;
}
.grade-pass    { color: var(--green); }
.grade-partial { color: var(--orange); }
.grade-fail    { color: var(--red); }
.grade-desc {
  font-size: 10.5px;
  color: var(--muted);
  margin-top: 3px;
  line-height: 1.35;
}

/* ── Content area ── */
.qa-content {
  flex: 1;
  overflow-y: auto;
  padding: 20px 24px;
}

.qa-section { display: none; }
.qa-section.active { display: block; }

.section-title {
  font-size: 15px;
  font-weight: 700;
  margin-bottom: 4px;
}
.section-subtitle {
  font-size: 12px;
  color: var(--muted);
  margin-bottom: 16px;
}

.check-list { display: flex; flex-direction: column; gap: 2px; }

.check {
  display: flex;
  align-items: flex-start;
  gap: 9px;
  padding: 7px 10px;
  border-radius: 6px;
  cursor: pointer;
  user-select: none;
  transition: background 0.1s;
}
.check:hover { background: #f8fafc; }

.check input[type="checkbox"] {
  appearance: none;
  -webkit-appearance: none;
  width: 14px;
  height: 14px;
  min-width: 14px;
  border: 1.5px solid #94a3b8;
  border-radius: 3px;
  margin-top: 1px;
  position: relative;
  cursor: pointer;
  transition: all 0.1s;
  background: #fff;
}
.check input[type="checkbox"]:checked {
  background: #1e293b;
  border-color: #1e293b;
}
.check input[type="checkbox"]:checked::after {
  content: '';
  position: absolute;
  left: 2px;
  top: 0px;
  width: 7px;
  height: 4px;
  border-left: 2px solid #fff;
  border-bottom: 2px solid #fff;
  transform: rotate(-45deg);
}

.check-label { font-size: 13px; line-height: 1.4; }

/* Non-critical: strikethrough + red when UNCHECKED */
.qa-section:not(#section-critical) .check:has(input:not(:checked)) .check-label {
  color: var(--red);
  text-decoration: line-through;
  opacity: 0.8;
}

/* Critical: bold red when CHECKED */
#section-critical .check:has(input:checked) { background: #fef2f2; }
#section-critical .check:has(input:checked) .check-label {
  color: var(--red);
  font-weight: 600;
}
#section-critical .check input[type="checkbox"]:checked {
  background: var(--red);
  border-color: var(--red);
}

/* ── Modal ── */
.qa-modal {
  display: none;
  position: fixed;
  inset: 0;
  z-index: 100;
  align-items: center;
  justify-content: center;
}
.qa-modal.open { display: flex; }
.modal-overlay {
  position: absolute;
  inset: 0;
  background: rgba(15, 23, 42, 0.4);
  backdrop-filter: blur(2px);
}
.modal-box {
  position: relative;
  background: #fff;
  border-radius: 12px;
  padding: 28px 28px 24px;
  max-width: 380px;
  width: 90%;
  box-shadow: 0 20px 60px rgba(0,0,0,0.2);
}
.modal-icon { font-size: 28px; margin-bottom: 10px; }
.modal-box h3 { font-size: 16px; font-weight: 700; margin-bottom: 8px; }
.modal-box p { font-size: 13px; color: var(--muted); line-height: 1.5; margin-bottom: 20px; }
.modal-box p strong { color: var(--text); }
.modal-btns { display: flex; flex-direction: column; gap: 8px; }
.modal-btns .btn { width: 100%; justify-content: center; display: flex; padding: 8px 16px; font-size: 13px; }
.modal-cancel-link {
  display: block;
  text-align: center;
  margin-top: 12px;
  font-size: 12px;
  color: var(--muted);
  cursor: pointer;
  text-decoration: underline;
}
.modal-cancel-link:hover { color: var(--text); }
  </style>
</head>
<body>

<!-- Top bar -->
<div class="qa-topbar">
  <span class="qa-logo">AI Import QA</span>
  <div class="qa-fields">
    <input id="field-project" type="text" placeholder="Project / customer" autocomplete="off">
    <input id="field-owner"   type="text" placeholder="QA Owner" autocomplete="off">
    <input id="field-url"     type="url"  placeholder="https://docs.example.com" autocomplete="off">
  </div>
  <div class="qa-actions">
    <button id="new-qa-btn"  class="btn btn-ghost">+ New QA</button>
    <button id="export-btn"  class="btn btn-primary">Export &amp; Copy Link</button>
  </div>
</div>

<!-- Body -->
<div class="qa-body">

  <!-- Sidebar -->
  <nav class="qa-sidebar">
    <div class="nav-group-label">Sections</div>

    <div class="qa-nav-item active" data-target="critical">
      <span class="nav-icon">⚠️</span>
      <span class="nav-label">Critical Failures</span>
      <span class="nav-badge badge-none" id="badge-critical"></span>
    </div>
    <div class="qa-nav-item" data-target="completeness">
      <span class="nav-icon">📋</span>
      <span class="nav-label">Completeness</span>
      <span class="nav-badge badge-none" id="badge-completeness"></span>
    </div>
    <div class="qa-nav-item" data-target="accuracy">
      <span class="nav-icon">🎯</span>
      <span class="nav-label">Accuracy</span>
      <span class="nav-badge badge-none" id="badge-accuracy"></span>
    </div>
    <div class="qa-nav-item" data-target="rendering">
      <span class="nav-icon">🖼️</span>
      <span class="nav-label">Rendering Fidelity</span>
      <span class="nav-badge badge-none" id="badge-rendering"></span>
    </div>
    <div class="qa-nav-item" data-target="ia">
      <span class="nav-icon">🗂️</span>
      <span class="nav-label">Info Architecture</span>
      <span class="nav-badge badge-none" id="badge-ia"></span>
    </div>
    <div class="qa-nav-item" data-target="code">
      <span class="nav-icon">💻</span>
      <span class="nav-label">Code Samples</span>
      <span class="nav-badge badge-none" id="badge-code"></span>
    </div>
    <div class="qa-nav-item" data-target="performance">
      <span class="nav-icon">⚡</span>
      <span class="nav-label">Performance</span>
      <span class="nav-badge badge-none" id="badge-performance"></span>
    </div>

    <!-- Auto grade -->
    <div class="qa-grade-box">
      <div class="grade-label">Auto Grade</div>
      <div class="grade-value grade-pass" id="auto-grade">PASS</div>
      <div class="grade-desc" id="grade-desc">No issues flagged</div>
    </div>
  </nav>

  <!-- Content -->
  <main class="qa-content">

    <div class="qa-section active" id="section-critical">
      <div class="section-title">⚠️ Critical Failure Conditions</div>
      <div class="section-subtitle">Check anything that applies. Any checked item triggers a FAIL grade.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox"><span class="check-label">Entire major sections missing</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Large numbers of skipped pages</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Missing API references</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Broad image/rendering failures</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Empty generated pages</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Fake AI-generated content</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Incorrect endpoint details</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Broken internal routing</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Broken markdown rendering</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Destroyed callouts</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Code/table corruption</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Unusable navigation</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Massive duplication</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Invalid JSON/examples</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Fake endpoints/parameters</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Unusable code samples</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Frequent rendering failures/crashes</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-completeness">
      <div class="section-title">📋 Completeness</div>
      <div class="section-subtitle">Uncheck anything that is failing or not verified.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">Major sections/pages imported</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Subsections/pages not skipped</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">API refs imported correctly</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No major navigation holes</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No empty categories/folders</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No obvious missing child pages</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Images/SVGs imported correctly</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Code examples imported</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Tables imported/readable</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">PDFs/download links preserved or flagged</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Page count roughly matches source</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Major nav groups match source</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-accuracy">
      <div class="section-title">🎯 Accuracy</div>
      <div class="section-subtitle">Uncheck anything that is failing or not verified.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">Technical meaning preserved</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No truncated content</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No hallucinated/generated filler</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No merged unrelated content</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No duplicated content blocks</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">HTTP methods correct</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">API paths correct</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Parameters/types correct</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Response codes correct</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Request/response examples preserved</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Internal links rewritten correctly</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">External links preserved correctly</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-rendering">
      <div class="section-title">🖼️ Rendering Fidelity</div>
      <div class="section-subtitle">Uncheck anything that is failing or not verified.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">Heading hierarchy logical</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">TOC generates correctly</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Pages readable/scannable</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Callouts/admonitions preserved</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Syntax highlighting works</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Code blocks readable</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Tables aligned/readable</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Nested lists preserved</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Images render correctly</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Relative asset paths resolved</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-ia">
      <div class="section-title">🗂️ Information Architecture</div>
      <div class="section-subtitle">Uncheck anything that is failing or not verified.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">Navigation grouping logical</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Parent/child relationships make sense</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Ordering predictable</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Landing pages placed correctly</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Slugs/page names clean</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No orphan pages</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No duplicate sections/pages</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Versions separated correctly</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-code">
      <div class="section-title">💻 Code Sample Quality</div>
      <div class="section-subtitle">Uncheck anything that is failing or not verified.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">Code samples syntactically valid</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Correct language labels</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Request bodies plausible</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Auth examples reasonable</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">JSON/code readable/formatted</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-performance">
      <div class="section-title">⚡ Performance &amp; Stability</div>
      <div class="section-subtitle">Uncheck anything that is failing or not verified.</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">Pages progressively appeared during import</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Sidebar responsive</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Pages load normally</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">No major lag/freezing</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Navigation usable during import</span></label>
      </div>
    </div>

  </main>
</div>

<!-- New QA confirmation modal -->
<div class="qa-modal" id="qa-modal">
  <div class="modal-overlay" id="modal-overlay"></div>
  <div class="modal-box">
    <div class="modal-icon">💾</div>
    <h3>Starting a new QA?</h3>
    <p>Make sure you've saved your work first — export your shareable link so you can come back to this one later.</p>
    <div class="modal-btns">
      <button id="modal-export-btn" class="btn btn-ghost">Export &amp; Copy Link First</button>
      <button id="modal-open-btn"   class="btn btn-primary">Open New Tab Anyway</button>
    </div>
    <span class="modal-cancel-link" id="modal-cancel-btn">Cancel</span>
  </div>
</div>

</body>
</html>
`}</HTMLBlock>

<br />
