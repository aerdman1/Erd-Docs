---
title: family test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
# Welcome to The Henry Howler

A living family archive — stories, photos, and history in one place.

<HTMLBlock>{`
<style>
  /* --- Home layout --- */
  .hh-home{display:grid;grid-template-columns:minmax(0,1fr) 340px;gap:24px;align-items:start;margin-top:18px;}
  .hh-main{min-width:0;}
  .hh-aside{border:1px solid rgba(0,0,0,.10);border-radius:14px;padding:16px;background:#fff;}
  .hh-aside h3{margin:0 0 10px 0;font-size:16px;font-weight:800;}
  .hh-aside .hh-sub{margin:0 0 14px 0;font-size:13px;opacity:.75;line-height:1.35;}

  /* Hero image */
  .hh-hero{border-radius:16px;overflow:hidden;border:1px solid rgba(0,0,0,.10);background:#f6f6f6;}
  .hh-hero img{display:block;width:100%;height:380px;object-fit:cover;}
  .hh-hero .hh-caption{padding:10px 12px;font-size:13px;opacity:.8;border-top:1px solid rgba(0,0,0,.06);}

  /* How-to section */
  .hh-howto{margin-top:18px;border:1px solid rgba(0,0,0,.10);border-radius:14px;padding:16px;background:#fff;}
  .hh-howto h2{margin:0 0 10px 0;font-size:18px;font-weight:900;}
  .hh-howto p{margin:0 0 12px 0;line-height:1.55;}
  .hh-howto ul{margin:0;padding-left:18px;line-height:1.75;}
  .hh-howto a{text-decoration:none;font-weight:650;}
  .hh-howto a:hover{text-decoration:underline;}

  /* Quick links row (optional) */
  .hh-quick{margin-top:18px;border:1px solid rgba(0,0,0,.10);border-radius:14px;padding:16px;background:#fff;}
  .hh-quick h2{margin:0 0 10px 0;font-size:18px;font-weight:900;}
  .hh-quick p{margin:0 0 14px 0;line-height:1.55;opacity:.9;}

  /* Recent posts list styling (JS will inject anchors with these classes) */
  .hh-recent{display:flex;flex-direction:column;gap:10px;}
  .hh-recent a{display:block;border:1px solid rgba(0,0,0,.10);border-radius:12px;padding:10px 12px;background:#fafafa;text-decoration:none;color:inherit;}
  .hh-recent a:hover{background:#f1f1f1;}
  .hh-recent .hh-title{font-weight:800;margin:0 0 2px 0;font-size:14px;}
  .hh-recent .hh-meta{font-size:12px;opacity:.7;margin:0;}
  .hh-note{font-size:12px;opacity:.75;margin:0;line-height:1.35;}

  /* Make Cards look a bit cleaner on this page */
  .CardsGrid .Card-title{font-weight:800;margin-top:10px;font-size:20px;}
  .CardsGrid .Card-content{line-height:1.35;}

  /* Responsive */
  @media (max-width: 980px){
    .hh-home{grid-template-columns:1fr;gap:18px;}
    .hh-hero img{height:280px;}
  }
</style>

<div class="hh-home">
  <div class="hh-main">

    <div class="hh-hero">
      <!-- Replace the src with your actual family image URL when ready -->
      <img src="https://placehold.co/1600x900/png?text=Family+Photo" alt="Family photo" />
      <div class="hh-caption">This is a placeholder — swap in a favorite family photo anytime.</div>
    </div>

    <section class="hh-howto">
      <h2>How to navigate</h2>
      <p>
        This site is organized into a few main areas so you can browse by time period, family line, or theme.
        If you’re not sure where to start, “Through the Decades” is the easiest on-ramp.
      </p>
      <ul>
        <li><a href="families-home">Through the Decades</a> — family articles organized by era</li>
        <li><a href="ancestors-home">Ancestors</a> — family lines, notes, and background</li>
        <li><a href="stories-and-memories-home">Odds &amp; Ends</a> — stories, memories, and one-offs</li>
        <li><a href="media-home">Media</a> — images, videos, and other files</li>
        <li><a href="other-home">Other</a> — misc. pages and experiments</li>
      </ul>
    </section>

    <section class="hh-quick">
      <h2>Browse the main sections</h2>
      <p>
        Pick a section below to jump in. Each area is meant to be bite-sized so it’s easy to add new memories over time.
      </p>
    </section>

  </div>

  <aside class="hh-aside">
    <h3>Recent posts</h3>
    <p class="hh-sub">Latest updates pulled from GitHub commit history.</p>

    <!-- IMPORTANT: Your *global* ReadMe Custom JavaScript will populate this -->
    <div id="hh-recent-posts">
      <p class="hh-note"><strong>Recent posts</strong>: loading…</p>
    </div>

    <p class="hh-note" style="margin-top:12px;">
      If nothing appears here, it usually means the global JS couldn’t map repo file paths to your ReadMe page slugs.
    </p>
  </aside>
</div>
`}</HTMLBlock>

<Cards columns={2} title="Explore">
  <Card title="Through The Decades" href="families-home" icon="fa-people-roof">
    Family articles organized by time period.
  </Card>

  <Card title="Ancestors" href="ancestors-home" icon="fa-tree">
    Browse family branches, notes, and background.
  </Card>

  <Card title="Odds & Ends" href="stories-and-memories-home" icon="fa-book-open">
    Stories, memories, and one-off posts.
  </Card>

  <Card title="Media" href="media-home" icon="fa-photo-film">
    Images, videos, and other media.
  </Card>
</Cards>

<Cards columns={1} title="Other">
  <Card title="Other" href="other-home" icon="fa-ellipsis">
    Miscellaneous pages and experiments.
  </Card>
</Cards>
