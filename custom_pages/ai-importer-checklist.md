---
title: AI 导入器检查清单
fullscreen: false
hidden: false
---
<HTMLBlock>{`
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>AI 导入 QA</title>
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
# section-critical .check:has(input:checked) { background: #fef2f2; }
# section-critical .check:has(input:checked) .check-label {
  color: var(--red);
  font-weight: 600;
}
# section-critical .check input[type="checkbox"]:checked {
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
  <span class="qa-logo">AI 导入 QA</span>
  <div class="qa-fields">
    <input id="field-project" type="text" placeholder="项目 / 客户" autocomplete="off">
    <input id="field-owner"   type="text" placeholder="QA 负责人" autocomplete="off">
    <input id="field-url"     type="url"  placeholder="https://docs.example.com" autocomplete="off">
  </div>
  <div class="qa-actions">
    <button id="new-qa-btn"  class="btn btn-ghost">+ 新建 QA</button>
    <button id="export-btn"  class="btn btn-primary">导出并复制链接</button>
  </div>
</div>

<!-- Body -->
<div class="qa-body">

  <!-- Sidebar -->
  <nav class="qa-sidebar">
    <div class="nav-group-label">章节</div>

    <div class="qa-nav-item active" data-target="critical">
      <span class="nav-icon">⚠️</span>
      <span class="nav-label">严重故障</span>
      <span class="nav-badge badge-none" id="badge-critical"></span>
    </div>
    <div class="qa-nav-item" data-target="completeness">
      <span class="nav-icon">📋</span>
      <span class="nav-label">完整性</span>
      <span class="nav-badge badge-none" id="badge-completeness"></span>
    </div>
    <div class="qa-nav-item" data-target="accuracy">
      <span class="nav-icon">🎯</span>
      <span class="nav-label">准确性</span>
      <span class="nav-badge badge-none" id="badge-accuracy"></span>
    </div>
    <div class="qa-nav-item" data-target="rendering">
      <span class="nav-icon">🖼️</span>
      <span class="nav-label">渲染保真度</span>
      <span class="nav-badge badge-none" id="badge-rendering"></span>
    </div>
    <div class="qa-nav-item" data-target="ia">
      <span class="nav-icon">🗂️</span>
      <span class="nav-label">信息架构</span>
      <span class="nav-badge badge-none" id="badge-ia"></span>
    </div>
    <div class="qa-nav-item" data-target="code">
      <span class="nav-icon">💻</span>
      <span class="nav-label">代码示例</span>
      <span class="nav-badge badge-none" id="badge-code"></span>
    </div>
    <div class="qa-nav-item" data-target="performance">
      <span class="nav-icon">⚡</span>
      <span class="nav-label">性能</span>
      <span class="nav-badge badge-none" id="badge-performance"></span>
    </div>

    <!-- Auto grade -->
    <div class="qa-grade-box">
      <div class="grade-label">自动评分</div>
      <div class="grade-value grade-pass" id="auto-grade">通过</div>
      <div class="grade-desc" id="grade-desc">未标记任何问题</div>
    </div>
  </nav>

  <!-- Content -->
  <main class="qa-content">

    <div class="qa-section active" id="section-critical">
      <div class="section-title">⚠️ 严重故障条件</div>
      <div class="section-subtitle">勾选所有适用项。勾选任意一项都将判定为不通过。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox"><span class="check-label">主要章节全部缺失</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">大量页面被跳过</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">缺失 API 参考文档</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">大范围图像/渲染失败</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">生成的页面为空</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">AI 生成的虚假内容</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">端点详情错误</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">内部路由损坏</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">Markdown 渲染损坏</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">提示框损坏</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">代码/表格损坏</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">导航不可用</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">大量重复内容</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">无效的 JSON/示例</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">虚假端点/参数</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">代码示例不可用</span></label>
        <label class="check"><input type="checkbox"><span class="check-label">频繁渲染失败/崩溃</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-completeness">
      <div class="section-title">📋 完整性</div>
      <div class="section-subtitle">取消勾选任何未通过或未验证的项。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">已导入主要章节/页面</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">未跳过子章节/页面</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">API 参考文档导入正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无重大导航缺失</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无空分类/文件夹</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无明显缺失的子页面</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">图像/SVG 导入正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">已导入代码示例</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">表格已导入且可读</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">PDF/下载链接已保留或已标记</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">页面数量与源大致吻合</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">主要导航分组与源一致</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-accuracy">
      <div class="section-title">🎯 准确性</div>
      <div class="section-subtitle">取消勾选任何未通过或未验证的项。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">保留技术原意</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无内容截断</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无幻觉/生成的填充内容</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">未合并无关内容</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无重复内容块</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">HTTP 方法正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">API 路径正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">参数/类型正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">响应状态码正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">保留请求/响应示例</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">内部链接重写正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">外部链接保留正确</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-rendering">
      <div class="section-title">🖼️ 渲染保真度</div>
      <div class="section-subtitle">取消勾选任何未通过或未验证的项。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">标题层级逻辑清晰</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">目录正确生成</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">页面可读且易于浏览</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">保留提示框/标注框</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">语法高亮正常生效</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">代码块清晰可读</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">表格对齐且可读</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">保留嵌套列表</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">图像渲染正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">相对资源路径已解析</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-ia">
      <div class="section-title">🗂️ 信息架构</div>
      <div class="section-subtitle">取消勾选任何未通过或未验证的项。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">导航分组逻辑合理</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">父子层级关系合理</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">排序符合预期</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">落地页位置正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">Slug/页面名称整洁规范</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无孤立页面</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无重复章节/页面</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">版本划分正确</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-code">
      <div class="section-title">💻 代码示例质量</div>
      <div class="section-subtitle">取消勾选任何未通过或未验证的项。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">代码示例语法有效</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">语言标签正确</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">请求体合理</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">认证示例合理</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">JSON/代码格式化且可读</span></label>
      </div>
    </div>

    <div class="qa-section" id="section-performance">
      <div class="section-title">⚡ 性能与稳定性</div>
      <div class="section-subtitle">取消勾选任何未通过或未验证的项。</div>
      <div class="check-list">
        <label class="check"><input type="checkbox" checked><span class="check-label">导入过程中页面渐进式显示</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">侧边栏响应灵敏</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">页面加载正常</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">无严重卡顿/假死</span></label>
        <label class="check"><input type="checkbox" checked><span class="check-label">导入过程中导航可用</span></label>
      </div>
    </div>

  </main>
</div>

<!-- New QA confirmation modal -->
<div class="qa-modal" id="qa-modal">
  <div class="modal-overlay" id="modal-overlay"></div>
  <div class="modal-box">
    <div class="modal-icon">💾</div>
    <h3>开始新的 QA？</h3>
    <p>请确保先保存您的工作——导出可共享的链接，以便日后返回查看。</p>
    <div class="modal-btns">
      <button id="modal-export-btn" class="btn btn-ghost">先导出并复制链接</button>
      <button id="modal-open-btn"   class="btn btn-primary">仍然在新标签页打开</button>
    </div>
    <span class="modal-cancel-link" id="modal-cancel-btn">取消</span>
  </div>
</div>

</body>
</html>
`}</HTMLBlock>

<br />
