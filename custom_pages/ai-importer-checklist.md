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
  <title>AI Import QA - Full Quality Checklist</title>
  <style>

.SuperHubCustomPage-content2y25YXtWEbiK {
    margin: 0 auto;
    max-width: 100%;
    }

.SuperHubCustomPage-content2y25YXtWEbiK {
    margin: 0 auto;
    max-width: 100%;
    padding: 10px;
    }

header.SuperHubCustomPage-content-header,.rm-Header_compact Header, header.Header3zzata9F_ZPQ.rm-Header_compact.Header_collapsible3n0YXfOvb_Al.rm-Header {
    display:none !important;
}
    :root {
      --text: #1f2933;
      --muted: #5f6b7a;
      --border: #d9dee7;
      --section: #f5f7fa;
      --critical: #fff3f0;
      --critical-border: #f1b8aa;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 28px;
      color: var(--text);
      font-family: Arial, Helvetica, sans-serif;
      background: #ffffff;
      line-height: 1.25;
    }

    .page {
      max-width: 1100px;
      margin: 0 auto;
    }

    header {
      border-bottom: 2px solid var(--border);
      margin-bottom: 16px;
      padding-bottom: 10px;
      display: flex;
      align-items: flex-start;
      justify-content: space-between;
      gap: 12px;
    }

    .header-left {
      flex: 1;
      min-width: 0;
    }

    h1 {
      margin: 0 0 6px;
      font-size: 24px;
      letter-spacing: -0.02em;
    }

    .intro {
      margin: 0 0 8px;
      color: var(--muted);
      font-size: 13px;
    }

    .header-fields {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
    }

    .header-fields input {
      padding: 5px 8px;
      font-size: 12px;
      border: 1.5px solid var(--border);
      border-radius: 6px;
      color: var(--text);
      outline: none;
      font-family: inherit;
      transition: border-color 0.15s;
    }

    .header-fields input:focus {
      border-color: #6b7280;
    }

    #field-project {
      flex: 1;
      min-width: 160px;
      max-width: 260px;
    }

    #field-url {
      flex: 2;
      min-width: 200px;
    }

    #export-btn {
      flex-shrink: 0;
      margin-top: 4px;
      padding: 6px 14px;
      font-size: 12px;
      font-weight: 600;
      border: 1.5px solid #1f2933;
      border-radius: 6px;
      background: #1f2933;
      color: #fff;
      cursor: pointer;
      white-space: nowrap;
      transition: background 0.15s, color 0.15s;
      font-family: inherit;
    }

    #export-btn:hover {
      background: #374151;
      border-color: #374151;
    }

    .grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
      align-items: start;
    }

    .section {
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
      break-inside: avoid;
      background: #fff;
    }

    .section h2 {
      margin: 0;
      padding: 8px 10px;
      font-size: 14px;
      background: var(--section);
      border-bottom: 1px solid var(--border);
    }

    .section.critical h2 {
      background: var(--critical);
      border-bottom-color: var(--critical-border);
    }

    .section.critical {
      border-color: var(--critical-border);
    }

    .checklist {
      padding: 8px 10px 9px;
    }

    .check {
      display: grid;
      grid-template-columns: 18px 1fr;
      gap: 5px;
      align-items: start;
      margin: 0 0 5px;
      font-size: 12px;
      cursor: pointer;
      user-select: none;
    }

    .check input[type="checkbox"] {
      appearance: none;
      -webkit-appearance: none;
      width: 12px;
      height: 12px;
      border: 1.5px solid #6b7280;
      border-radius: 2px;
      margin-top: 1px;
      flex-shrink: 0;
      position: relative;
      cursor: pointer;
      transition: background 0.1s, border-color 0.1s;
    }

    .check input[type="checkbox"]:hover {
      border-color: #374151;
    }

    .check input[type="checkbox"]:checked {
      background: #1f2933;
      border-color: #1f2933;
    }

    .check input[type="checkbox"]:checked::after {
      content: '';
      position: absolute;
      left: 1px;
      top: -1px;
      width: 7px;
      height: 4px;
      border-left: 1.5px solid #fff;
      border-bottom: 1.5px solid #fff;
      transform: rotate(-45deg);
    }

    /* Non-critical: strike through when UNCHECKED (flagged as failing) */
    .section:not(.critical) .check:has(input:not(:checked)) > span {
      color: #dc2626;
      text-decoration: line-through;
    }

    /* Critical: highlight when CHECKED (flagged as a critical failure) */
    .section.critical .check:has(input:checked) > span {
      color: #dc2626;
      font-weight: 600;
    }

    .grading {
      margin-top: 12px;
      border: 1px solid var(--border);
      border-radius: 10px;
      overflow: hidden;
    }

    .grading h2 {
      margin: 0;
      padding: 8px 10px;
      font-size: 14px;
      background: var(--section);
      border-bottom: 1px solid var(--border);
    }

    .grade-row {
      display: grid;
      grid-template-columns: 95px 1fr;
      gap: 8px;
      padding: 7px 10px;
      border-bottom: 1px solid var(--border);
      font-size: 12px;
    }

    .grade-row:last-child {
      border-bottom: 0;
    }

    .grade {
      font-weight: 700;
    }

    @media print {
      body { padding: 0.35in; }
      .page { max-width: none; }
      h1 { font-size: 20px; }
      .intro { font-size: 11px; }
      .grid { grid-template-columns: 1fr 1fr; gap: 8px; }
      .section { border-radius: 6px; }
      .section h2, .grading h2 { font-size: 12px; padding: 6px 8px; }
      .checklist { padding: 6px 8px; }
      .check { font-size: 10px; margin-bottom: 3px; grid-template-columns: 15px 1fr; }
      .grading { margin-top: 8px; border-radius: 6px; }
      .grade-row { font-size: 10px; padding: 5px 8px; }
      #export-btn { display: none; }
      .header-fields input { border: none; padding: 0; font-size: 11px; color: var(--muted); }
    }
  </style>
</head>
<body>
  <main class="page">
    <header>
      <div class="header-left">
        <h1>AI Import QA - Full Quality Checklist</h1>
        <p class="intro">Uncheck anything that is failing. Check any critical failure conditions that apply. Notify Erdman immediately if any critical issue is discovered.</p>
        <div class="header-fields">
          <input id="field-project" type="text" placeholder="Project / customer name" autocomplete="off">
          <input id="field-url" type="url" placeholder="https://docs.example.com" autocomplete="off">
        </div>
      </div>
      <button id="export-btn">Export &amp; Copy Link</button>
    </header>

    <section class="grid">

      <!-- CRITICAL FIRST — unchecked by default, check to flag a failure -->
      <div class="section critical">
        <h2>⚠️ Critical Failure Conditions — check any that apply</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Entire major sections missing</span></label>
          <label class="check"><input type="checkbox"><span>Large numbers of skipped pages</span></label>
          <label class="check"><input type="checkbox"><span>Missing API references</span></label>
          <label class="check"><input type="checkbox"><span>Broad image/rendering failures</span></label>
          <label class="check"><input type="checkbox"><span>Empty generated pages</span></label>
          <label class="check"><input type="checkbox"><span>Fake AI-generated content</span></label>
          <label class="check"><input type="checkbox"><span>Incorrect endpoint details</span></label>
          <label class="check"><input type="checkbox"><span>Broken internal routing</span></label>
          <label class="check"><input type="checkbox"><span>Broken markdown rendering</span></label>
          <label class="check"><input type="checkbox"><span>Destroyed callouts</span></label>
          <label class="check"><input type="checkbox"><span>Code/table corruption</span></label>
          <label class="check"><input type="checkbox"><span>Unusable navigation</span></label>
          <label class="check"><input type="checkbox"><span>Massive duplication</span></label>
          <label class="check"><input type="checkbox"><span>Invalid JSON/examples</span></label>
          <label class="check"><input type="checkbox"><span>Fake endpoints/parameters</span></label>
          <label class="check"><input type="checkbox"><span>Unusable code samples</span></label>
          <label class="check"><input type="checkbox"><span>Frequent rendering failures/crashes</span></label>
        </div>
      </div>

      <!-- COMPLETENESS — checked by default, uncheck to flag -->
      <div class="section">
        <h2>Completeness — uncheck anything failing</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox" checked><span>Major sections/pages imported</span></label>
          <label class="check"><input type="checkbox" checked><span>Subsections/pages not skipped</span></label>
          <label class="check"><input type="checkbox" checked><span>API refs imported correctly</span></label>
          <label class="check"><input type="checkbox" checked><span>No major navigation holes</span></label>
          <label class="check"><input type="checkbox" checked><span>No empty categories/folders</span></label>
          <label class="check"><input type="checkbox" checked><span>No obvious missing child pages</span></label>
          <label class="check"><input type="checkbox" checked><span>Images/SVGs imported correctly</span></label>
          <label class="check"><input type="checkbox" checked><span>Code examples imported</span></label>
          <label class="check"><input type="checkbox" checked><span>Tables imported/readable</span></label>
          <label class="check"><input type="checkbox" checked><span>PDFs/download links preserved or flagged</span></label>
          <label class="check"><input type="checkbox" checked><span>Page count roughly matches source</span></label>
          <label class="check"><input type="checkbox" checked><span>Major nav groups match source</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Accuracy — uncheck anything failing</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox" checked><span>Technical meaning preserved</span></label>
          <label class="check"><input type="checkbox" checked><span>No truncated content</span></label>
          <label class="check"><input type="checkbox" checked><span>No hallucinated/generated filler</span></label>
          <label class="check"><input type="checkbox" checked><span>No merged unrelated content</span></label>
          <label class="check"><input type="checkbox" checked><span>No duplicated content blocks</span></label>
          <label class="check"><input type="checkbox" checked><span>HTTP methods correct</span></label>
          <label class="check"><input type="checkbox" checked><span>API paths correct</span></label>
          <label class="check"><input type="checkbox" checked><span>Parameters/types correct</span></label>
          <label class="check"><input type="checkbox" checked><span>Response codes correct</span></label>
          <label class="check"><input type="checkbox" checked><span>Request/response examples preserved</span></label>
          <label class="check"><input type="checkbox" checked><span>Internal links rewritten correctly</span></label>
          <label class="check"><input type="checkbox" checked><span>External links preserved correctly</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Rendering Fidelity — uncheck anything failing</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox" checked><span>Heading hierarchy logical</span></label>
          <label class="check"><input type="checkbox" checked><span>TOC generates correctly</span></label>
          <label class="check"><input type="checkbox" checked><span>Pages readable/scannable</span></label>
          <label class="check"><input type="checkbox" checked><span>Callouts/admonitions preserved</span></label>
          <label class="check"><input type="checkbox" checked><span>Syntax highlighting works</span></label>
          <label class="check"><input type="checkbox" checked><span>Code blocks readable</span></label>
          <label class="check"><input type="checkbox" checked><span>Tables aligned/readable</span></label>
          <label class="check"><input type="checkbox" checked><span>Nested lists preserved</span></label>
          <label class="check"><input type="checkbox" checked><span>Images render correctly</span></label>
          <label class="check"><input type="checkbox" checked><span>Relative asset paths resolved</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Information Architecture — uncheck anything failing</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox" checked><span>Navigation grouping logical</span></label>
          <label class="check"><input type="checkbox" checked><span>Parent/child relationships make sense</span></label>
          <label class="check"><input type="checkbox" checked><span>Ordering predictable</span></label>
          <label class="check"><input type="checkbox" checked><span>Landing pages placed correctly</span></label>
          <label class="check"><input type="checkbox" checked><span>Slugs/page names clean</span></label>
          <label class="check"><input type="checkbox" checked><span>No orphan pages</span></label>
          <label class="check"><input type="checkbox" checked><span>No duplicate sections/pages</span></label>
          <label class="check"><input type="checkbox" checked><span>Versions separated correctly</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Code Sample Quality — uncheck anything failing</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox" checked><span>Code samples syntactically valid</span></label>
          <label class="check"><input type="checkbox" checked><span>Correct language labels</span></label>
          <label class="check"><input type="checkbox" checked><span>Request bodies plausible</span></label>
          <label class="check"><input type="checkbox" checked><span>Auth examples reasonable</span></label>
          <label class="check"><input type="checkbox" checked><span>JSON/code readable/formatted</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Performance &amp; Stability — uncheck anything failing</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox" checked><span>Pages progressively appeared during import</span></label>
          <label class="check"><input type="checkbox" checked><span>Sidebar responsive</span></label>
          <label class="check"><input type="checkbox" checked><span>Pages load normally</span></label>
          <label class="check"><input type="checkbox" checked><span>No major lag/freezing</span></label>
          <label class="check"><input type="checkbox" checked><span>Navigation usable during import</span></label>
        </div>
      </div>

      <div class="grading">
        <h2>Final Grading</h2>
        <div class="grade-row"><span class="grade">PASS</span><span>Launch-quality with only minor cleanup needed</span></div>
        <div class="grade-row"><span class="grade">PARTIAL</span><span>Usable but requires noticeable cleanup before customer-ready</span></div>
        <div class="grade-row"><span class="grade">FAIL</span><span>Major issues make the import unreliable or unusable</span></div>
      </div>

    </section>
  </main>
</body>
</html>
`}</HTMLBlock>

<br />
