---
title: family test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<HTMLBlock>{`
<style>
  /* Recent posts box */
  .hh-aside{border:1px solid rgba(0,0,0,.08);border-radius:12px;padding:16px;background:#fff;}
  .hh-aside h3{margin:0 0 10px 0;font-size:16px;font-weight:700;}
  .hh-aside .hh-sub{margin:0 0 14px 0;font-size:13px;opacity:.75;line-height:1.35;}
  .hh-recent{display:flex;flex-direction:column;gap:10px;}
  .hh-recent a{display:block;border:1px solid rgba(0,0,0,.08);border-radius:10px;padding:10px 12px;background:#fafafa;text-decoration:none;color:inherit;}
  .hh-recent a:hover{background:#f2f2f2;}
  .hh-recent .hh-title{font-weight:700;margin:0 0 2px 0;font-size:14px;}
  .hh-recent .hh-meta{font-size:12px;opacity:.7;margin:0;}
  .hh-note{font-size:12px;opacity:.75;margin:0;}
</style>

<aside class="hh-aside">
  <h3>Recent posts</h3>
  <p class="hh-sub">Latest updates pulled from GitHub commit history.</p>

  <!-- JS will replace this content -->
  <div id="hh-recent-posts">
    <p class="hh-note"><strong>Recent posts</strong>: loading…</p>
  </div>
</aside>
`}</HTMLBlock>
