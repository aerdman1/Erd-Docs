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
    }

    .box {
      width: 12px;
      height: 12px;
      border: 1.5px solid #6b7280;
      border-radius: 2px;
      margin-top: 1px;
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
          <div class="check"><span class="box"></span><span>Major sections/pages imported</span></div>
          <div class="check"><span class="box"></span><span>Subsections/pages not skipped</span></div>
          <div class="check"><span class="box"></span><span>API refs imported correctly</span></div>
          <div class="check"><span class="box"></span><span>No major navigation holes</span></div>
          <div class="check"><span class="box"></span><span>No empty categories/folders</span></div>
          <div class="check"><span class="box"></span><span>No obvious missing child pages</span></div>
          <div class="check"><span class="box"></span><span>Images/SVGs imported correctly</span></div>
          <div class="check"><span class="box"></span><span>Code examples imported</span></div>
          <div class="check"><span class="box"></span><span>Tables imported/readable</span></div>
          <div class="check"><span class="box"></span><span>PDFs/download links preserved or flagged</span></div>
          <div class="check"><span class="box"></span><span>Page count roughly matches source</span></div>
          <div class="check"><span class="box"></span><span>Major nav groups match source</span></div>
        </div>
      </div>

      <div class="section">
        <h2>Accuracy</h2>
        <div class="checklist">
          <div class="check"><span class="box"></span><span>Technical meaning preserved</span></div>
          <div class="check"><span class="box"></span><span>No truncated content</span></div>
          <div class="check"><span class="box"></span><span>No hallucinated/generated filler</span></div>
          <div class="check"><span class="box"></span><span>No merged unrelated content</span></div>
          <div class="check"><span class="box"></span><span>No duplicated content blocks</span></div>
          <div class="check"><span class="box"></span><span>HTTP methods correct</span></div>
          <div class="check"><span class="box"></span><span>API paths correct</span></div>
          <div class="check"><span class="box"></span><span>Parameters/types correct</span></div>
          <div class="check"><span class="box"></span><span>Response codes correct</span></div>
          <div class="check"><span class="box"></span><span>Request/response examples preserved</span></div>
          <div class="check"><span class="box"></span><span>Internal links rewritten correctly</span></div>
          <div class="check"><span class="box"></span><span>External links preserved correctly</span></div>
        </div>
      </div>

      <div class="section">
        <h2>Rendering Fidelity</h2>
        <div class="checklist">
          <div class="check"><span class="box"></span><span>Heading hierarchy logical</span></div>
          <div class="check"><span class="box"></span><span>TOC generates correctly</span></div>
          <div class="check"><span class="box"></span><span>Pages readable/scannable</span></div>
          <div class="check"><span class="box"></span><span>Callouts/admonitions preserved</span></div>
          <div class="check"><span class="box"></span><span>Syntax highlighting works</span></div>
          <div class="check"><span class="box"></span><span>Code blocks readable</span></div>
          <div class="check"><span class="box"></span><span>Tables aligned/readable</span></div>
          <div class="check"><span class="box"></span><span>Nested lists preserved</span></div>
          <div class="check"><span class="box"></span><span>Images render correctly</span></div>
          <div class="check"><span class="box"></span><span>Relative asset paths resolved</span></div>
        </div>
      </div>

      <div class="section">
        <h2>Information Architecture</h2>
        <div class="checklist">
          <div class="check"><span class="box"></span><span>Navigation grouping logical</span></div>
          <div class="check"><span class="box"></span><span>Parent/child relationships make sense</span></div>
          <div class="check"><span class="box"></span><span>Ordering predictable</span></div>
          <div class="check"><span class="box"></span><span>Landing pages placed correctly</span></div>
          <div class="check"><span class="box"></span><span>Slugs/page names clean</span></div>
          <div class="check"><span class="box"></span><span>No orphan pages</span></div>
          <div class="check"><span class="box"></span><span>No duplicate sections/pages</span></div>
          <div class="check"><span class="box"></span><span>Versions separated correctly</span></div>
        </div>
      </div>

      <div class="section">
        <h2>Code Sample Quality</h2>
        <div class="checklist">
          <div class="check"><span class="box"></span><span>Code samples syntactically valid</span></div>
          <div class="check"><span class="box"></span><span>Correct language labels</span></div>
          <div class="check"><span class="box"></span><span>Request bodies plausible</span></div>
          <div class="check"><span class="box"></span><span>Auth examples reasonable</span></div>
          <div class="check"><span class="box"></span><span>JSON/code readable/formatted</span></div>
        </div>
      </div>

      <div class="section">
        <h2>Performance & Stability</h2>
        <div class="checklist">
          <div class="check"><span class="box"></span><span>Pages progressively appeared during import</span></div>
          <div class="check"><span class="box"></span><span>Sidebar responsive</span></div>
          <div class="check"><span class="box"></span><span>Pages load normally</span></div>
          <div class="check"><span class="box"></span><span>No major lag/freezing</span></div>
          <div class="check"><span class="box"></span><span>Navigation usable during import</span></div>
        </div>
      </div>

      <div class="section critical">
        <h2>Critical Failure Conditions</h2>
        <div class="checklist">
          <div class="check"><span class="box"></span><span>Entire major sections missing</span></div>
          <div class="check"><span class="box"></span><span>Large numbers of skipped pages</span></div>
          <div class="check"><span class="box"></span><span>Missing API references</span></div>
          <div class="check"><span class="box"></span><span>Broad image/rendering failures</span></div>
          <div class="check"><span class="box"></span><span>Empty generated pages</span></div>
          <div class="check"><span class="box"></span><span>Fake AI-generated content</span></div>
          <div class="check"><span class="box"></span><span>Incorrect endpoint details</span></div>
          <div class="check"><span class="box"></span><span>Broken internal routing</span></div>
          <div class="check"><span class="box"></span><span>Broken markdown rendering</span></div>
          <div class="check"><span class="box"></span><span>Destroyed callouts</span></div>
          <div class="check"><span class="box"></span><span>Code/table corruption</span></div>
          <div class="check"><span class="box"></span><span>Unusable navigation</span></div>
          <div class="check"><span class="box"></span><span>Massive duplication</span></div>
          <div class="check"><span class="box"></span><span>Invalid JSON/examples</span></div>
          <div class="check"><span class="box"></span><span>Fake endpoints/parameters</span></div>
          <div class="check"><span class="box"></span><span>Unusable code samples</span></div>
          <div class="check"><span class="box"></span><span>Frequent rendering failures/crashes</span></div>
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
