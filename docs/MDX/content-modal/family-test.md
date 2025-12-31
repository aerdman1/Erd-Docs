---
title: family test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
# Welcome to The Henry Howler!

A collection and collaboration of family history, current and future events.

<HTMLBlock>{`
<style>
  /* --- Henry Howler Home Layout --- */
  .hh-home{display:grid;grid-template-columns:minmax(0,1fr) 320px;gap:24px;align-items:start;margin-top:18px;}
  .hh-main{min-width:0;}
  .hh-aside{position:sticky;top:18px;border:1px solid rgba(0,0,0,.08);border-radius:12px;padding:16px;background:#fff;}
  .hh-aside h3{margin:0 0 10px 0;font-size:16px;font-weight:700;}
  .hh-aside .hh-sub{margin:0 0 14px 0;font-size:13px;opacity:.75;line-height:1.35;}

  /* Hero image */
  .hh-hero{border-radius:14px;overflow:hidden;border:1px solid rgba(0,0,0,.08);background:#f6f6f6;}
  .hh-hero img{display:block;width:100%;height:360px;object-fit:cover;}
  .hh-hero .hh-caption{padding:10px 12px;font-size:13px;opacity:.8;border-top:1px solid rgba(0,0,0,.06);}

  /* How-to / navigation section */
  .hh-howto{margin-top:18px;border:1px solid rgba(0,0,0,.08);border-radius:12px;padding:16px;background:#fff;}
  .hh-howto h2{margin:0 0 10px 0;font-size:18px;font-weight:800;}
  .hh-howto p{margin:0 0 12px 0;line-height:1.5;}
  .hh-howto ul{margin:0;padding-left:18px;line-height:1.7;}
  .hh-howto a{text-decoration:none;}
  .hh-howto a:hover{text-decoration:underline;}

  /* Recent posts list */
  .hh-recent{display:flex;flex-direction:column;gap:10px;}
  .hh-recent a{display:block;border:1px solid rgba(0,0,0,.08);border-radius:10px;padding:10px 12px;background:#fafafa;text-decoration:none;color:inherit;}
  .hh-recent a:hover{background:#f2f2f2;}
  .hh-recent .hh-title{font-weight:700;margin:0 0 2px 0;font-size:14px;}
  .hh-recent .hh-meta{font-size:12px;opacity:.7;margin:0;}
  .hh-recent .hh-note{font-size:12px;opacity:.75;margin:8px 0 0 0;}

  /* Responsive */
  @media (max-width: 980px){
    .hh-home{grid-template-columns:1fr;gap:18px;}
    .hh-aside{position:static;}
    .hh-hero img{height:280px;}
  }
</style>

<div class="hh-home">
  <div class="hh-main">
    <div class="hh-hero">
      <!-- Replace this src with your own family image whenever ready -->
      <img
        src="https://placehold.co/1600x900/png?text=Family+Photo"
        alt="Family photo"
      />
      <div class="hh-caption">Tip: swap this placeholder with your favorite family photo (any public image URL works).</div>
    </div>

    <section class="hh-howto">
      <h2>How to navigate</h2>
      <p>
        Use the sections on the left to explore stories, photos, and family history by time period, branch, or theme.
        If you’re not sure where to start, begin with “Through the Decades” for a quick timeline view.
      </p>
      <ul>
        <li><a href="families-home">Through the Decades</a> — family articles organized by era</li>
        <li><a href="ancestors-home">Ancestors</a> — family lines, notes, and background</li>
        <li><a href="stories-and-memories-home">Odds &amp; Ends</a> — stories, memories, and one-offs</li>
        <li><a href="media-home">Media</a> — images, videos, and other files</li>
        <li><a href="other-home">Other</a> — misc. pages and experiments</li>
      </ul>
    </section>
  </div>

  <aside class="hh-aside">
    <h3>Recent posts</h3>
    <p class="hh-sub">A quick list of the latest additions. (For now, these are placeholders — replace with real links as you add articles.)</p>

    <div class="hh-recent">
      <a href="families-home">
        <p class="hh-title">Through the Decades — start here</p>
        <p class="hh-meta">Timeline overview</p>
      </a>
      <a href="ancestors-home">
        <p class="hh-title">Ancestors — family branches</p>
        <p class="hh-meta">Browse by line</p>
      </a>
      <a href="stories-and-memories-home">
        <p class="hh-title">Odds &amp; Ends — stories &amp; memories</p>
        <p class="hh-meta">Short reads</p>
      </a>
      <a href="media-home">
        <p class="hh-title">Media — photos and videos</p>
        <p class="hh-meta">Gallery</p>
      </a>

      <p class="hh-note"><strong>Note:</strong> Once you have true “recent articles,” we can swap this to a tighter list (titles + dates) and style it like a mini feed.</p>
    </div>
  </aside>
</div>
`}</HTMLBlock>
