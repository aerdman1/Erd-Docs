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
    }

    h1 {
      margin: 0 0 6px;
      font-size: 24px;
      letter-spacing: -0.02em;
    }

    .intro {
      margin: 0;
      color: var(--muted);
      font-size: 13px;
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

    .check:has(input:checked) > span {
      color: var(--muted);
      text-decoration: line-through;
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
      body {
        padding: 0.35in;
      }

      .page {
        max-width: none;
      }

      h1 {
        font-size: 20px;
      }

      .intro {
        font-size: 11px;
      }

      .grid {
        grid-template-columns: 1fr 1fr;
        gap: 8px;
      }

      .section {
        border-radius: 6px;
      }

      .section h2,
      .grading h2 {
        font-size: 12px;
        padding: 6px 8px;
      }

      .checklist {
        padding: 6px 8px;
      }

      .check {
        font-size: 10px;
        margin-bottom: 3px;
        grid-template-columns: 15px 1fr;
      }

      .box {
        width: 10px;
        height: 10px;
      }

      .grading {
        margin-top: 8px;
        border-radius: 6px;
      }

      .grade-row {
        font-size: 10px;
        padding: 5px 8px;
      }
    }
  </style>
</head>
<body>
  <main class="page">
    <header>
      <h1>AI Import QA - Full Quality Checklist</h1>
      <p class="intro">Use after initial validation passes. Notify Erdman immediately if any critical issue is discovered.</p>
    </header>

    <section class="grid">
      <div class="section">
        <h2>Completeness</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Major sections/pages imported</span></label>
          <label class="check"><input type="checkbox"><span>Subsections/pages not skipped</span></label>
          <label class="check"><input type="checkbox"><span>API refs imported correctly</span></label>
          <label class="check"><input type="checkbox"><span>No major navigation holes</span></label>
          <label class="check"><input type="checkbox"><span>No empty categories/folders</span></label>
          <label class="check"><input type="checkbox"><span>No obvious missing child pages</span></label>
          <label class="check"><input type="checkbox"><span>Images/SVGs imported correctly</span></label>
          <label class="check"><input type="checkbox"><span>Code examples imported</span></label>
          <label class="check"><input type="checkbox"><span>Tables imported/readable</span></label>
          <label class="check"><input type="checkbox"><span>PDFs/download links preserved or flagged</span></label>
          <label class="check"><input type="checkbox"><span>Page count roughly matches source</span></label>
          <label class="check"><input type="checkbox"><span>Major nav groups match source</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Accuracy</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Technical meaning preserved</span></label>
          <label class="check"><input type="checkbox"><span>No truncated content</span></label>
          <label class="check"><input type="checkbox"><span>No hallucinated/generated filler</span></label>
          <label class="check"><input type="checkbox"><span>No merged unrelated content</span></label>
          <label class="check"><input type="checkbox"><span>No duplicated content blocks</span></label>
          <label class="check"><input type="checkbox"><span>HTTP methods correct</span></label>
          <label class="check"><input type="checkbox"><span>API paths correct</span></label>
          <label class="check"><input type="checkbox"><span>Parameters/types correct</span></label>
          <label class="check"><input type="checkbox"><span>Response codes correct</span></label>
          <label class="check"><input type="checkbox"><span>Request/response examples preserved</span></label>
          <label class="check"><input type="checkbox"><span>Internal links rewritten correctly</span></label>
          <label class="check"><input type="checkbox"><span>External links preserved correctly</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Rendering Fidelity</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Heading hierarchy logical</span></label>
          <label class="check"><input type="checkbox"><span>TOC generates correctly</span></label>
          <label class="check"><input type="checkbox"><span>Pages readable/scannable</span></label>
          <label class="check"><input type="checkbox"><span>Callouts/admonitions preserved</span></label>
          <label class="check"><input type="checkbox"><span>Syntax highlighting works</span></label>
          <label class="check"><input type="checkbox"><span>Code blocks readable</span></label>
          <label class="check"><input type="checkbox"><span>Tables aligned/readable</span></label>
          <label class="check"><input type="checkbox"><span>Nested lists preserved</span></label>
          <label class="check"><input type="checkbox"><span>Images render correctly</span></label>
          <label class="check"><input type="checkbox"><span>Relative asset paths resolved</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Information Architecture</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Navigation grouping logical</span></label>
          <label class="check"><input type="checkbox"><span>Parent/child relationships make sense</span></label>
          <label class="check"><input type="checkbox"><span>Ordering predictable</span></label>
          <label class="check"><input type="checkbox"><span>Landing pages placed correctly</span></label>
          <label class="check"><input type="checkbox"><span>Slugs/page names clean</span></label>
          <label class="check"><input type="checkbox"><span>No orphan pages</span></label>
          <label class="check"><input type="checkbox"><span>No duplicate sections/pages</span></label>
          <label class="check"><input type="checkbox"><span>Versions separated correctly</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Code Sample Quality</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Code samples syntactically valid</span></label>
          <label class="check"><input type="checkbox"><span>Correct language labels</span></label>
          <label class="check"><input type="checkbox"><span>Request bodies plausible</span></label>
          <label class="check"><input type="checkbox"><span>Auth examples reasonable</span></label>
          <label class="check"><input type="checkbox"><span>JSON/code readable/formatted</span></label>
        </div>
      </div>

      <div class="section">
        <h2>Performance & Stability</h2>
        <div class="checklist">
          <label class="check"><input type="checkbox"><span>Pages progressively appeared during import</span></label>
          <label class="check"><input type="checkbox"><span>Sidebar responsive</span></label>
          <label class="check"><input type="checkbox"><span>Pages load normally</span></label>
          <label class="check"><input type="checkbox"><span>No major lag/freezing</span></label>
          <label class="check"><input type="checkbox"><span>Navigation usable during import</span></label>
        </div>
      </div>

      <div class="section critical">
        <h2>Critical Failure Conditions</h2>
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
