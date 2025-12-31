---
title: family test
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<HTMLBlock>{`
<div id="hh-recent-posts">
  <p class="hh-note"><strong>Recent posts</strong>: loading…</p>
</div>

<script>
(function () {
  var OWNER = "aerdman1";
  var REPO = "henryhowler";

  // Try these refs in order. If your sync uses a tag/branch like v1.0, this covers it.
  var REFS = ["main", "master", "v1.0"];

  // Where your “posts” live in the repo
  var PATHS = ["docs"]; // add "custom_pages" if you want those too: ["docs","custom_pages"]

  var MAX_ITEMS = 2;

  function el() { return document.getElementById("hh-recent-posts"); }

  function htmlEscape(s){
    return String(s).replace(/[&<>"']/g, function(c){
      return ({ "&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;" })[c];
    });
  }

  // Convert repo file path -> ReadMe doc slug/href
  function fileToHref(filename) {
    // docs/families-home.mdx -> families-home
    // docs/ancestors/john-henry.mdx -> ancestors/john-henry
    var slug = filename.replace(/^docs\//, "").replace(/\.(md|mdx)$/i, "");
    return slug; // relative links work fine in ReadMe
  }

  // Friendly title fallback from filename
  function fileToTitle(filename) {
    var base = filename.split("/").pop().replace(/\.(md|mdx)$/i, "");
    return base.replace(/[-_]+/g, " ").replace(/\b\w/g, function(m){ return m.toUpperCase(); });
  }

  // Optional: try to read the actual title from the file (frontmatter title: or first # heading)
  function fetchTitleFromRaw(ref, filename) {
    var raw = "https://raw.githubusercontent.com/" + OWNER + "/" + REPO + "/" + ref + "/" + filename;
    return fetch(raw).then(function(r){ return r.ok ? r.text() : ""; }).then(function(txt){
      if (!txt) return null;
      var fm = txt.match(/^---[\\s\\S]*?\\btitle:\\s*["']?(.+?)["']?\\s*(?:\\r?\\n)[\\s\\S]*?---/m);
      if (fm && fm[1]) return fm[1].trim();
      var h1 = txt.match(/^\\s*#\\s+(.+)\\s*$/m);
      if (h1 && h1[1]) return h1[1].trim();
      return null;
    }).catch(function(){ return null; });
  }

  // GitHub REST: list commits (supports per_page) :contentReference[oaicite:1]{index=1}
  function listCommits(ref, path) {
    var url = "https://api.github.com/repos/" + OWNER + "/" + REPO + "/commits?sha=" + encodeURIComponent(ref) +
              "&path=" + encodeURIComponent(path) + "&per_page=12";
    return fetch(url).then(function(r){ return r.ok ? r.json() : Promise.reject(new Error("commits " + r.status)); });
  }

  // GitHub REST: get commit (includes files changed)
  function getCommit(ref, sha) {
    var url = "https://api.github.com/repos/" + OWNER + "/" + REPO + "/commits/" + encodeURIComponent(sha);
    return fetch(url).then(function(r){ return r.ok ? r.json() : Promise.reject(new Error("commit " + r.status)); });
  }

  function render(items){
    var target = el();
    if (!target) return;

    if (!items.length) {
      target.innerHTML = "<p class='hh-note'><strong>Recent posts</strong>: coming soon.</p>";
      return;
    }

    var out = "";
    out += "<h3 style='margin:0 0 10px 0;font-size:16px;font-weight:700;'>Recent posts</h3>";
    out += "<div class='hh-recent'>";

    items.forEach(function(it){
      out += "<a href='" + htmlEscape(it.href) + "'>";
      out += "<p class='hh-title'>" + htmlEscape(it.title) + "</p>";
      out += "<p class='hh-meta'>Updated " + htmlEscape(it.updatedLabel) + "</p>";
      out += "</a>";
    });

    out += "</div>";
    target.innerHTML = out;
  }

  function tryRef(i){
    if (i >= REFS.length) {
      render([]);
      return;
    }
    var ref = REFS[i];

    // Pull a small window of commits for each path, then inspect commit files
    Promise.all(PATHS.map(function(p){ return listCommits(ref, p); }))
      .then(function(allCommitLists){
        var shas = [];
        allCommitLists.forEach(function(list){
          (list || []).forEach(function(c){ if (c && c.sha) shas.push(c.sha); });
        });

        // De-dupe SHAs
        var seenSha = {};
        shas = shas.filter(function(s){ if (seenSha[s]) return false; seenSha[s]=true; return true; }).slice(0, 10);

        return Promise.all(shas.map(function(sha){ return getCommit(ref, sha).catch(function(){ return null; }); }))
          .then(function(commitDetails){
            var fileMap = {}; // filename -> { updatedAt, title?, href }
            commitDetails.forEach(function(cd){
              if (!cd || !cd.files || !cd.commit) return;
              var updatedAt = (cd.commit.committer && cd.commit.committer.date) || (cd.commit.author && cd.commit.author.date) || null;
              if (!updatedAt) return;

              cd.files.forEach(function(f){
                if (!f || !f.filename) return;

                // Only docs markdown
                var name = f.filename;
                var isDoc = name.indexOf("docs/") === 0; // keep tight to your use case
                var isMd = /\.mdx?$/i.test(name);
                if (!isDoc || !isMd) return;

                var existing = fileMap[name];
                if (!existing || existing.updatedAt < updatedAt) {
                  fileMap[name] = {
                    filename: name,
                    updatedAt: updatedAt,
                    href: fileToHref(name),
                    title: null
                  };
                }
              });
            });

            var files = Object.keys(fileMap).map(function(k){ return fileMap[k]; })
              .sort(function(a,b){ return a.updatedAt < b.updatedAt ? 1 : -1; })
              .slice(0, MAX_ITEMS);

            // Try to fetch real titles; fall back to filename-based titles
            return Promise.all(files.map(function(f){
              return fetchTitleFromRaw(ref, f.filename).then(function(t){
                var d = new Date(f.updatedAt);
                f.title = t || fileToTitle(f.filename);
                f.updatedLabel = isFinite(d.getTime()) ? d.toLocaleDateString() : "recently";
                return f;
              });
            }));
          })
          .then(function(items){
            render(items);
          });
      })
      .catch(function(){
        // If ref doesn't exist, try next ref
        tryRef(i + 1);
      });
  }

  tryRef(0);
})();
</script>
`}</HTMLBlock>
