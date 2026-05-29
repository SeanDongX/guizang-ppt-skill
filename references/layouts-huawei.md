# Layouts · Style C Huawei Corporate

这套版式使用 Huawei 企业汇报视觉语言:白/浅灰底、华为红、右上品牌位、左上红方块标题锚点、章节红带、红色圆形图标、灰色信息条、流程箭头、数据柱状图、人物头像、地图定位、圆心辐射和照片证据页。

## 生成前必读

### A. 文件和类名来源

- 模板文件:`assets/template-huawei.html`
- 主题色:`references/themes-huawei.md`
- 不要把 Style A / Style B 的类名混进来。Huawei 模板使用自己的类名系统。
- 每页 `<section>` 必须写 `data-layout="Hxx"`。
- 页面内必须保留 `.brand-lockup` 或使用 cover/closing 里的品牌锁定区域。
- `.brand-mark` 已内置 Huawei logo SVG mask;生成华为 PPT 时保留 `<span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span>` 结构。

### B. 图片规则

| 场景 | 推荐比例 | 容器 |
|---|---|---|
| 主图 / 产品图 | 16:9 或 16:10 | `.image-frame.r-16x9` / `.image-frame.r-16x10` |
| 人物 / 现场照片 | 4:3 或 16:9 | `.image-frame.r-4x3` / `.image-frame.r-16x9` |
| 多图证据墙 | 全部统一 16:9 | `.grid-3` + `.image-frame.r-16x9` |
| 白底 UI / 图表 | 16:10 + contain | `.image-frame.r-16x10.fit-contain` |

图片放在目标 deck 的 `images/` 目录下,命名建议:`01-cover.jpg`、`06-product.png`。

### C. 版式节奏

8-10 页 deck 推荐节奏:

| 页码 | 布局 | 用途 |
|---|---|---|
| 01 | H01 | 封面 |
| 02 | H02 | 目录 |
| 03 | H03 | 章节幕封 |
| 04 | H04 | 观点说明 |
| 05 | H07 | 数据页 |
| 06 | H08 | 流程页 |
| 07 | H09 | 图片/证据页 |
| 08 | H06 | 时间线 |
| 09 | H05 | 能力/方案卡片 |
| 10 | H10 | 收束 |

12-18 页 deck 可以在 H04-H09 中间插入 H11-H36 扩展版式,让内容形状更贴近企业汇报场景:

| 内容形状 | 优先版式 |
|---|---|
| 前言 / 引言 / 说明书式正文 | H11 |
| 图文报告 / 案例摘要 / 业务新闻 | H12 / H25 |
| 多张照片横向展示 | H13 |
| 团队 / 专家 / 管理层 | H14 |
| KPI + 数字看板 | H15 |
| 柱线组合 / 趋势分析 | H16 / H22 |
| 能力模型 / 生态关系 / 关键要素 | H17 |
| 阶段路线 / 斜向推进 | H18 / H24 |
| 圆形案例 / 客户现场 / 业务节点 | H19 |
| 图标能力矩阵 | H20 |
| 区域布局 / 网点 / 项目地图 | H21 |
| 齿轮协同 / 闭环流程 | H23 |
| 隐喻表达 / 方案对比 | H26 |
| 商业计划 / 市场 / 融资 / 定价 | H27-H36 |

## H01 · Cover

适合首页。使用大 logo、白灰背景、底部红色波浪。

```html
<section class="slide hw-cover" data-layout="H01" data-animate="cover">
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div class="cover-shell">
    <div class="cover-title-wrap">
      <div class="cover-badge" data-anim>
        <span class="brand-mark" aria-hidden="true"></span>
      </div>
      <div class="kicker" data-anim>ANNUAL REPORT / 2026</div>
      <h1 class="h-hero" data-anim>华为公司<br/>总结PPT</h1>
      <p class="lead cover-subtitle" data-anim>业绩报告 / 工作计划总结 / 商务路演等应用</p>
    </div>

    <div class="cover-visual" aria-hidden="true">
      <span class="orb red" style="width:6vw;height:6vw;right:10vw;top:3vh"></span>
      <span class="orb" style="width:12vw;height:12vw;right:0;top:16vh"></span>
      <span class="orb red" style="width:2.6vw;height:2.6vw;right:18vw;top:34vh"></span>
      <span class="orb" style="width:5vw;height:5vw;right:26vw;top:8vh"></span>
    </div>
  </div>

  <div class="cover-wave" aria-hidden="true"></div>
  <div class="cover-meta">
    <div>汇报人: [姓名]</div>
    <div>部门: [部门名称]</div>
  </div>
</section>
```

## H02 · Agenda

目录页。左侧红色目录块,右侧灰色条目,所有条目统一使用 `.agenda-item`,不要添加 `active` 标记。

```html
<section class="slide" data-layout="H02" data-animate="agenda">
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div class="agenda-layout">
    <div class="red-panel" data-anim>
      <div class="kicker" style="color:rgba(255,255,255,.72)">CONTENT</div>
      <h2 class="h-xl" style="margin-top:2vh">目录</h2>
      <div class="en" style="margin-top:2vh">CONTENT</div>
    </div>

    <div class="agenda-list">
      <div class="agenda-item" data-anim><div class="idx">01</div><div class="txt">添加章节标题内容</div></div>
      <div class="agenda-item" data-anim><div class="idx">02</div><div class="txt">添加章节标题内容</div></div>
      <div class="agenda-item" data-anim><div class="idx">03</div><div class="txt">添加章节标题内容</div></div>
      <div class="agenda-item" data-anim><div class="idx">04</div><div class="txt">添加章节标题内容</div></div>
      <div class="agenda-item" data-anim><div class="idx">05</div><div class="txt">添加章节标题内容</div></div>
    </div>
  </div>
</section>
```

## H03 · Section Divider

章节幕封。适合“01 工作完成情况 / 02 成功项目展示”一类章节切换。

```html
<section class="slide" data-layout="H03" data-animate="section">
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div class="section-layout">
    <div data-anim>
      <div class="section-no">01</div>
      <div class="kicker">SECTION ONE</div>
      <h2 class="h-xl" style="margin-top:1.8vh">工作完成情况</h2>
      <p class="lead" style="margin-top:2vh">添加章节说明文字,控制在一到两行。</p>
    </div>

    <div class="red-panel" data-anim>
      <div class="kicker" style="color:rgba(255,255,255,.72)">KEY MESSAGE</div>
      <h3 class="h-md" style="margin-top:2vh">用一句话概括本章节最重要的结论</h3>
    </div>
  </div>
</section>
```

## Page Number Rule

页码由模板脚本自动生成在左下角 `.page-no`。不要在 `.chrome` 右侧手写页码;右侧保留空 `<div></div>` 或放简短元信息。

## H04 · Title Body

最通用正文页。左上红色方块标题锚点 + 右上品牌位 + 正文卡片。

```html
<section class="slide" data-layout="H04" data-animate="body">
  <div class="chrome">
    <div class="l"><span class="square"></span><span>添加标题文本</span></div>
    <div>01 / 10</div>
  </div>
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="height:100%;display:grid;grid-template-rows:auto 1fr;gap:4.8vh;padding-top:7vh">
    <div class="content-stack" data-anim>
      <div class="kicker">INTRODUCTION</div>
      <h2 class="h-xl">前言 / Introduction</h2>
      <div class="red-rule" style="width:8vw"></div>
    </div>

    <div class="grid-2" style="align-items:start">
      <div class="card flat" data-anim>
        <p class="body-copy">请输入正文内容。此页适合承载背景介绍、项目说明、阶段总结和管理层摘要。建议每段不超过 3 行,避免堆成文档页。</p>
      </div>
      <div class="card" data-anim>
        <div class="card-title">核心结论</div>
        <p class="card-body">把最关键的信息放在这里,用红色标题和白卡片形成稳定的企业汇报感。</p>
      </div>
    </div>
  </div>
</section>
```

## H05 · Three Cards

三项能力、三阶段、三条策略。

```html
<section class="slide" data-layout="H05" data-animate="cards">
  <div class="chrome">
    <div class="l"><span class="square"></span><span>添加标题文本</span></div>
    <div>02 / 10</div>
  </div>
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim>
      <div class="kicker">THREE PRIORITIES</div>
      <h2 class="h-xl">三项核心能力</h2>
    </div>

    <div class="grid-3" style="margin-top:6vh">
      <div class="card" data-anim>
        <div class="icon-disc"><i data-lucide="target"></i></div>
        <div class="card-title">目标牵引</div>
        <p class="card-body">添加说明文字,强调阶段目标与业务结果的对应关系。</p>
      </div>
      <div class="card" data-anim>
        <div class="icon-disc"><i data-lucide="workflow"></i></div>
        <div class="card-title">流程闭环</div>
        <p class="card-body">添加说明文字,强调跨团队协同、交付节奏与复盘机制。</p>
      </div>
      <div class="card" data-anim>
        <div class="icon-disc"><i data-lucide="bar-chart-3"></i></div>
        <div class="card-title">数据度量</div>
        <p class="card-body">添加说明文字,强调指标体系、风险预警与持续改进。</p>
      </div>
    </div>
  </div>
</section>
```

## H06 · Vertical Timeline

年度演进、项目里程碑、产品发布节奏。

```html
<section class="slide" data-layout="H06" data-animate="timeline">
  <div class="chrome">
    <div class="l"><span class="square"></span><span>添加标题文本</span></div>
    <div>03 / 10</div>
  </div>
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim>
      <div class="kicker">MILESTONE</div>
      <h2 class="h-xl">项目关键里程碑</h2>
    </div>

    <div class="timeline-v" style="margin-top:5vh">
      <div>
        <div class="tl-card" data-anim><div class="year">2024 Q1</div><p class="card-body">完成项目立项与目标拆解。</p></div>
        <div class="tl-card" data-anim><div class="year">2024 Q3</div><p class="card-body">完成核心系统上线与试点。</p></div>
      </div>
      <div class="tl-axis" data-anim>
        <div class="tl-dot">01</div>
        <div class="tl-dot">02</div>
        <div class="tl-dot">03</div>
      </div>
      <div>
        <div class="tl-card" data-anim><div class="year">2024 Q2</div><p class="card-body">完成方案评审和资源锁定。</p></div>
        <div class="tl-card" data-anim><div class="year">2024 Q4</div><p class="card-body">完成规模化推广与复盘。</p></div>
      </div>
    </div>
  </div>
</section>
```

## H07 · Data Bars

数据对比、达成率、排名、增长情况。

```html
<section class="slide" data-layout="H07" data-animate="data">
  <div class="chrome">
    <div class="l"><span class="square"></span><span>添加标题文本</span></div>
    <div>04 / 10</div>
  </div>
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="padding-top:8vh">
    <div class="grid-12" style="align-items:end">
      <div class="span-5 content-stack" data-anim>
        <div class="kicker">PERFORMANCE</div>
        <h2 class="h-xl">关键指标达成</h2>
        <p class="lead">用一页讲清楚最重要的业务结果,不要塞满表格。</p>
        <div>
          <div class="stat-big">86%</div>
          <div class="meta">TARGET COMPLETION</div>
        </div>
      </div>

      <div class="span-7 card" data-anim>
        <div class="bar-chart">
          <div class="bar-row"><span>市场</span><div class="bar-track"><div class="bar-fill" style="--v:86%"></div></div><strong>86%</strong></div>
          <div class="bar-row"><span>交付</span><div class="bar-track"><div class="bar-fill" style="--v:74%"></div></div><strong>74%</strong></div>
          <div class="bar-row"><span>质量</span><div class="bar-track"><div class="bar-fill" style="--v:92%"></div></div><strong>92%</strong></div>
          <div class="bar-row"><span>效率</span><div class="bar-track"><div class="bar-fill" style="--v:68%"></div></div><strong>68%</strong></div>
          <div class="bar-row"><span>满意度</span><div class="bar-track"><div class="bar-fill" style="--v:80%"></div></div><strong>80%</strong></div>
        </div>
      </div>
    </div>
  </div>
</section>
```

## H08 · Process Arrow

横向流程、方法论步骤、项目推进路径。

```html
<section class="slide" data-layout="H08" data-animate="process">
  <div class="chrome">
    <div class="l"><span class="square"></span><span>添加标题文本</span></div>
    <div>05 / 10</div>
  </div>
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim>
      <div class="kicker">WORKFLOW</div>
      <h2 class="h-xl">标准化推进流程</h2>
    </div>

    <div class="process" style="margin-top:7vh">
      <div class="process-step" data-anim>
        <div class="num-pill">01</div>
        <div class="card-title">目标定义</div>
        <p class="card-body">明确项目目标、边界、负责人和度量方式。</p>
      </div>
      <div class="process-step" data-anim>
        <div class="num-pill">02</div>
        <div class="card-title">方案设计</div>
        <p class="card-body">完成路径拆解、资源评估和关键风险识别。</p>
      </div>
      <div class="process-step" data-anim>
        <div class="num-pill">03</div>
        <div class="card-title">执行交付</div>
        <p class="card-body">按里程碑推进,通过周节奏管理进展。</p>
      </div>
      <div class="process-step" data-anim>
        <div class="num-pill">04</div>
        <div class="card-title">复盘优化</div>
        <p class="card-body">沉淀方法、数据和下一阶段改进项。</p>
      </div>
    </div>
  </div>
</section>
```

## H09 · Image Evidence Grid

照片、产品图、案例图、客户现场图。多图必须统一比例和高度。

```html
<section class="slide" data-layout="H09" data-animate="images">
  <div class="chrome">
    <div class="l"><span class="square"></span><span>添加标题文本</span></div>
    <div>06 / 10</div>
  </div>
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim>
      <div class="kicker">EVIDENCE</div>
      <h2 class="h-xl">案例与现场证据</h2>
    </div>

    <div class="grid-3" style="margin-top:5vh">
      <div data-anim>
        <div class="image-frame r-16x9"><img src="images/06-case-01.jpg" alt="案例图片 1"></div>
        <div class="caption">案例说明文字,控制在一行到两行。</div>
      </div>
      <div data-anim>
        <div class="image-frame r-16x9"><img src="images/06-case-02.jpg" alt="案例图片 2"></div>
        <div class="caption">案例说明文字,控制在一行到两行。</div>
      </div>
      <div data-anim>
        <div class="image-frame r-16x9"><img src="images/06-case-03.jpg" alt="案例图片 3"></div>
        <div class="caption">案例说明文字,控制在一行到两行。</div>
      </div>
    </div>
  </div>
</section>
```

## H10 · Closing

结束页。适合“感谢聆听 / 演示完毕”。

```html
<section class="slide dark" data-layout="H10" data-animate="closing">
  <div class="brand-lockup">
    <span class="brand-mark" aria-hidden="true"></span>
    <span>HUAWEI</span>
  </div>

  <div style="height:100%;display:grid;align-content:center;gap:3vh;max-width:62vw">
    <div class="cover-badge" data-anim>
      <span class="brand-mark" aria-hidden="true"></span>
    </div>
    <div class="kicker" data-anim>THANK YOU</div>
    <h2 class="h-hero" data-anim>演示完毕<br/>感谢聆听</h2>
    <p class="lead" data-anim>业绩报告 / 工作计划总结 / 商务路演等应用</p>
  </div>
</section>
```

## H11 · Framed Foreword

长图里多次出现的“前言 / Introduction”页:上方小标题,中间白底正文框,四角红色标记。适合前言、背景说明、政策解读、研究口径。

```html
<section class="slide" data-layout="H11" data-animate="foreword">
  <div class="chrome"><div class="l"><span class="square"></span><span>前言 / INTRODUCTION</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:9vh;display:grid;gap:4vh">
    <div class="content-stack" data-anim>
      <div class="kicker">INTRODUCTION</div>
      <h2 class="h-xl">前言</h2>
    </div>
    <div class="card flat" data-anim style="position:relative;max-width:72vw;margin:auto;padding:5vh 5vw">
      <span style="position:absolute;left:1.4vw;top:1.4vh;width:2.2vw;height:2px;background:var(--brand-red)"></span>
      <span style="position:absolute;left:1.4vw;top:1.4vh;width:2px;height:2.2vw;background:var(--brand-red)"></span>
      <span style="position:absolute;right:1.4vw;bottom:1.4vh;width:2.2vw;height:2px;background:var(--brand-red)"></span>
      <span style="position:absolute;right:1.4vw;bottom:1.4vh;width:2px;height:2.2vw;background:var(--brand-red)"></span>
      <p class="body-copy">添加前言正文。每段控制在 2-3 行,总字数不超过 180 字。此页用于建立汇报背景、范围、目标和口径,不要放复杂图表。</p>
    </div>
  </div>
</section>
```

## H12 · Media Report Split

上方横向图片或新闻截图,下方多段说明。适合业务案例、会议纪要、产品发布、项目实证。

```html
<section class="slide" data-layout="H12" data-animate="media-report">
  <div class="chrome"><div class="l"><span class="square"></span><span>案例摘要</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh;display:grid;grid-template-columns:.92fr 1.08fr;gap:3vw;align-items:start">
    <div data-anim>
      <div class="image-frame r-16x10"><img src="images/12-case.jpg" alt="案例主图"></div>
      <div class="caption">图片说明 / 客户现场 / 产品截图 / 会议照片。</div>
    </div>
    <div class="content-stack" data-anim>
      <div class="kicker">CASE STUDY</div>
      <h2 class="h-xl">用一句话概括案例价值</h2>
      <div class="card flat"><p class="body-copy">第一段写背景,第二段写动作,第三段写结果。右侧正文比图片略高,形成传统企业报告里的图文页节奏。</p></div>
      <div class="grid-3">
        <div><div class="num-pill">01</div><p class="card-body">关键事实</p></div>
        <div><div class="num-pill">02</div><p class="card-body">关键动作</p></div>
        <div><div class="num-pill">03</div><p class="card-body">关键结果</p></div>
      </div>
    </div>
  </div>
</section>
```

## H13 · Captioned Image Strip

横向 5 图证据条:每张图下方一个红色标签。适合活动回顾、项目阶段、产品矩阵、客户案例墙。

```html
<section class="slide" data-layout="H13" data-animate="image-strip">
  <div class="chrome"><div class="l"><span class="square"></span><span>成果展示</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim>
      <div class="kicker">GALLERY</div>
      <h2 class="h-xl">阶段成果展示</h2>
    </div>
    <div class="grid-4" style="grid-template-columns:repeat(5,1fr);margin-top:5vh">
      <div data-anim><div class="image-frame r-16x9"><img src="images/13-01.jpg" alt="成果图片 1"></div><div class="caption" style="background:var(--brand-red);color:#fff;text-align:center;padding:.8vh">成果一</div></div>
      <div data-anim><div class="image-frame r-16x9"><img src="images/13-02.jpg" alt="成果图片 2"></div><div class="caption" style="background:var(--brand-red);color:#fff;text-align:center;padding:.8vh">成果二</div></div>
      <div data-anim><div class="image-frame r-16x9"><img src="images/13-03.jpg" alt="成果图片 3"></div><div class="caption" style="background:var(--brand-red);color:#fff;text-align:center;padding:.8vh">成果三</div></div>
      <div data-anim><div class="image-frame r-16x9"><img src="images/13-04.jpg" alt="成果图片 4"></div><div class="caption" style="background:var(--brand-red);color:#fff;text-align:center;padding:.8vh">成果四</div></div>
      <div data-anim><div class="image-frame r-16x9"><img src="images/13-05.jpg" alt="成果图片 5"></div><div class="caption" style="background:var(--brand-red);color:#fff;text-align:center;padding:.8vh">成果五</div></div>
    </div>
  </div>
</section>
```

## H14 · Team Profiles

四位人物头像 + 姓名职务 + 简介。适合团队介绍、专家阵容、项目成员、客户代表。

```html
<section class="slide" data-layout="H14" data-animate="profiles">
  <div class="chrome"><div class="l"><span class="square"></span><span>团队介绍</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">TEAM</div><h2 class="h-xl">核心团队</h2></div>
    <div class="grid-4" style="margin-top:5vh">
      <div class="card" data-anim style="text-align:center"><div class="image-frame" style="width:8vw;height:8vw;border-radius:999px;margin:auto;overflow:hidden"><img src="images/14-person-01.jpg" alt="成员头像 1"></div><div class="card-title" style="margin-top:2vh">姓名</div><p class="card-body">职位 / 负责方向 / 一句话简介。</p></div>
      <div class="card" data-anim style="text-align:center"><div class="image-frame" style="width:8vw;height:8vw;border-radius:999px;margin:auto;overflow:hidden"><img src="images/14-person-02.jpg" alt="成员头像 2"></div><div class="card-title" style="margin-top:2vh">姓名</div><p class="card-body">职位 / 负责方向 / 一句话简介。</p></div>
      <div class="card" data-anim style="text-align:center"><div class="image-frame" style="width:8vw;height:8vw;border-radius:999px;margin:auto;overflow:hidden"><img src="images/14-person-03.jpg" alt="成员头像 3"></div><div class="card-title" style="margin-top:2vh">姓名</div><p class="card-body">职位 / 负责方向 / 一句话简介。</p></div>
      <div class="card" data-anim style="text-align:center"><div class="image-frame" style="width:8vw;height:8vw;border-radius:999px;margin:auto;overflow:hidden"><img src="images/14-person-04.jpg" alt="成员头像 4"></div><div class="card-title" style="margin-top:2vh">姓名</div><p class="card-body">职位 / 负责方向 / 一句话简介。</p></div>
    </div>
  </div>
</section>
```

## H15 · KPI Dashboard

左侧堆叠柱或柱状图,右侧大数字与指标解释。适合经营结果、年度目标、预算、人效、质量指标。

```html
<section class="slide" data-layout="H15" data-animate="kpi-dashboard">
  <div class="chrome"><div class="l"><span class="square"></span><span>关键数据</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div class="grid-12" style="padding-top:9vh;align-items:end">
    <div class="span-7 card" data-anim>
      <div class="kicker">YEARLY PERFORMANCE</div>
      <div style="height:42vh;display:flex;align-items:end;gap:1.2vw;margin-top:4vh;border-bottom:1px solid var(--line)">
        <div style="height:38%;width:4vw;background:#d8dde4"></div><div style="height:52%;width:4vw;background:#d8dde4"></div><div style="height:64%;width:4vw;background:var(--brand-red)"></div><div style="height:76%;width:4vw;background:var(--brand-red)"></div><div style="height:88%;width:4vw;background:var(--brand-red)"></div>
      </div>
    </div>
    <div class="span-5 content-stack" data-anim>
      <div class="stat-big">123,456</div>
      <div class="card-title">核心指标名称</div>
      <p class="lead">右侧只解释一个最重要数字,补充同比、环比、目标完成率。</p>
      <div class="red-rule" style="width:10vw"></div>
    </div>
  </div>
</section>
```

## H16 · Combo Chart

柱状图 + 折线 / 趋势点 + 旁侧结论。适合增长趋势、成本收益、质量变化、渠道对比。

```html
<section class="slide" data-layout="H16" data-animate="combo-chart">
  <div class="chrome"><div class="l"><span class="square"></span><span>趋势分析</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">TREND</div><h2 class="h-xl">增长趋势分析</h2></div>
    <div class="grid-12" style="margin-top:5vh;align-items:stretch">
      <div class="span-8 card" data-anim>
        <div style="height:42vh;display:grid;grid-template-columns:repeat(6,1fr);align-items:end;gap:1vw;border-bottom:1px solid var(--line);position:relative">
          <span style="position:absolute;left:4%;right:4%;top:42%;border-top:3px solid var(--brand-red);transform:rotate(-8deg);transform-origin:left center"></span>
          <span style="position:absolute;left:18%;top:47%;width:.9vw;height:.9vw;border-radius:999px;background:var(--brand-red)"></span>
          <span style="position:absolute;left:51%;top:36%;width:.9vw;height:.9vw;border-radius:999px;background:var(--brand-red)"></span>
          <span style="position:absolute;right:12%;top:30%;width:.9vw;height:.9vw;border-radius:999px;background:var(--brand-red)"></span>
          <div style="height:30%;background:#d8dde4"></div><div style="height:46%;background:#d8dde4"></div><div style="height:58%;background:var(--brand-red)"></div><div style="height:74%;background:var(--brand-red)"></div><div style="height:62%;background:#d8dde4"></div><div style="height:82%;background:var(--brand-red)"></div>
        </div>
      </div>
      <div class="span-4 card" data-anim>
        <div class="num-pill">01</div><div class="card-title">趋势判断</div><p class="card-body">用 2-3 个 bullet 解释波峰、波谷和拐点,不要把所有明细塞进图表。</p>
      </div>
    </div>
  </div>
</section>
```

## H17 · Central Hub

中心圆 + 周围节点。长图里的灯泡、圆形关系图、生态协同页都属于这个结构。适合能力模型、生态关系、战略抓手、系统架构。

```html
<section class="slide" data-layout="H17" data-animate="hub">
  <div class="chrome"><div class="l"><span class="square"></span><span>能力模型</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">MODEL</div><h2 class="h-xl">中心能力模型</h2></div>
    <div style="position:relative;height:52vh;margin-top:2vh" data-anim>
      <div style="position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);width:10vw;height:10vw;border-radius:999px;background:var(--brand-red);color:#fff;display:grid;place-items:center;font-weight:900">核心</div>
      <div style="position:absolute;left:16%;top:12%" class="card"><div class="card-title">能力一</div><p class="card-body">说明文字</p></div>
      <div style="position:absolute;right:16%;top:12%" class="card"><div class="card-title">能力二</div><p class="card-body">说明文字</p></div>
      <div style="position:absolute;left:18%;bottom:6%" class="card"><div class="card-title">能力三</div><p class="card-body">说明文字</p></div>
      <div style="position:absolute;right:18%;bottom:6%" class="card"><div class="card-title">能力四</div><p class="card-body">说明文字</p></div>
    </div>
  </div>
</section>
```

## H18 · Diagonal Roadmap

斜向上升路径 + 红色圆点。适合阶段推进、成长路径、项目路线、能力成熟度。

```html
<section class="slide" data-layout="H18" data-animate="diagonal-roadmap">
  <div class="chrome"><div class="l"><span class="square"></span><span>推进路线</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">ROADMAP</div><h2 class="h-xl">四阶段推进路线</h2></div>
    <div style="position:relative;height:46vh;margin-top:5vh" data-anim>
      <div style="position:absolute;left:10%;bottom:10%;right:10%;height:1px;background:var(--line-strong);transform:rotate(-12deg)"></div>
      <div style="position:absolute;left:10%;bottom:9%"><div class="icon-disc"><i data-lucide="flag"></i></div><div class="card-title">启动</div></div>
      <div style="position:absolute;left:34%;bottom:22%"><div class="icon-disc"><i data-lucide="settings"></i></div><div class="card-title">建设</div></div>
      <div style="position:absolute;left:58%;bottom:35%"><div class="icon-disc"><i data-lucide="rocket"></i></div><div class="card-title">推广</div></div>
      <div style="position:absolute;left:80%;bottom:48%"><div class="icon-disc"><i data-lucide="trophy"></i></div><div class="card-title">达成</div></div>
    </div>
  </div>
</section>
```

## H19 · Circular Case Cluster

多张圆形图片围绕结论排列。适合客户案例、区域项目、活动现场、生态伙伴。

```html
<section class="slide" data-layout="H19" data-animate="case-cluster">
  <div class="chrome"><div class="l"><span class="square"></span><span>案例集群</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">CASES</div><h2 class="h-xl">重点案例分布</h2></div>
    <div style="position:relative;height:52vh;margin-top:2vh" data-anim>
      <div style="position:absolute;left:42%;top:34%;width:13vw;height:13vw;border-radius:999px;background:var(--brand-red);color:#fff;display:grid;place-items:center;font-weight:900;text-align:center">核心<br/>成果</div>
      <div class="image-frame" style="position:absolute;left:15%;top:5%;width:12vw;height:12vw;border-radius:999px;overflow:hidden"><img src="images/19-case-01.jpg" alt="圆形案例 1"></div>
      <div class="image-frame" style="position:absolute;right:16%;top:8%;width:10vw;height:10vw;border-radius:999px;overflow:hidden"><img src="images/19-case-02.jpg" alt="圆形案例 2"></div>
      <div class="image-frame" style="position:absolute;left:24%;bottom:4%;width:10vw;height:10vw;border-radius:999px;overflow:hidden"><img src="images/19-case-03.jpg" alt="圆形案例 3"></div>
      <div class="image-frame" style="position:absolute;right:25%;bottom:2%;width:12vw;height:12vw;border-radius:999px;overflow:hidden"><img src="images/19-case-04.jpg" alt="圆形案例 4"></div>
    </div>
  </div>
</section>
```

## H20 · Icon Matrix

2x4 或 3x3 图标矩阵。适合能力清单、产品模块、服务范围、工具箱。

```html
<section class="slide" data-layout="H20" data-animate="icon-matrix">
  <div class="chrome"><div class="l"><span class="square"></span><span>能力矩阵</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">CAPABILITY</div><h2 class="h-xl">八项核心能力</h2></div>
    <div class="grid-4" style="margin-top:5vh">
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="cloud"></i></div><div class="card-title">能力一</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="database"></i></div><div class="card-title">能力二</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="shield"></i></div><div class="card-title">能力三</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="cpu"></i></div><div class="card-title">能力四</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="network"></i></div><div class="card-title">能力五</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="workflow"></i></div><div class="card-title">能力六</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="bar-chart-3"></i></div><div class="card-title">能力七</div><p class="card-body">一句话说明。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="settings"></i></div><div class="card-title">能力八</div><p class="card-body">一句话说明。</p></div>
    </div>
  </div>
</section>
```

## H21 · Map Locations

地图轮廓 + 红色定位点 + 右侧列表。适合区域布局、项目网点、市场覆盖、客户分布。

```html
<section class="slide" data-layout="H21" data-animate="map">
  <div class="chrome"><div class="l"><span class="square"></span><span>区域布局</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div class="grid-12" style="padding-top:9vh;align-items:center">
    <div class="span-8 card" data-anim style="height:54vh;position:relative;background:#f1f3f6">
      <div style="position:absolute;left:12%;top:18%;right:12%;bottom:18%;background:#dfe3e8;clip-path:polygon(12% 38%,31% 20%,54% 24%,75% 36%,84% 60%,62% 75%,34% 68%,18% 58%)"></div>
      <span style="position:absolute;left:38%;top:38%;width:1.6vw;height:1.6vw;border-radius:999px;background:var(--brand-red)"></span>
      <span style="position:absolute;left:55%;top:45%;width:1.6vw;height:1.6vw;border-radius:999px;background:var(--brand-red)"></span>
      <span style="position:absolute;left:48%;top:58%;width:1.6vw;height:1.6vw;border-radius:999px;background:var(--brand-red)"></span>
    </div>
    <div class="span-4 content-stack" data-anim>
      <div class="kicker">REGION</div><h2 class="h-md">重点区域覆盖</h2>
      <div class="agenda-list">
        <div class="agenda-item"><div class="idx">01</div><div class="txt">区域 A</div></div>
        <div class="agenda-item"><div class="idx">02</div><div class="txt">区域 B</div></div>
        <div class="agenda-item"><div class="idx">03</div><div class="txt">区域 C</div></div>
      </div>
    </div>
  </div>
</section>
```

## H22 · Growth Staircase

逐级上升台阶 / 阶梯柱。适合年度增长、阶段目标、成熟度爬坡、收入预测。

```html
<section class="slide" data-layout="H22" data-animate="staircase">
  <div class="chrome"><div class="l"><span class="square"></span><span>增长路径</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">GROWTH</div><h2 class="h-xl">关键指标持续爬坡</h2></div>
    <div style="display:flex;align-items:end;gap:1vw;height:46vh;margin-top:5vh" data-anim>
      <div style="height:25%;width:13vw;background:#dfe3e8;padding:1.4vh">10%</div>
      <div style="height:42%;width:13vw;background:#cfd5dd;padding:1.4vh">18%</div>
      <div style="height:58%;width:13vw;background:#b7c0ca;padding:1.4vh">26%</div>
      <div style="height:74%;width:13vw;background:var(--brand-red);color:#fff;padding:1.4vh">34%</div>
      <div style="height:88%;width:13vw;background:var(--brand-red-dark);color:#fff;padding:1.4vh">40%</div>
    </div>
  </div>
</section>
```

## H23 · Gear Process

齿轮 / 闭环协同。适合组织协作、流程机制、平台运转、生态联动。

```html
<section class="slide" data-layout="H23" data-animate="gear-process">
  <div class="chrome"><div class="l"><span class="square"></span><span>协同机制</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">OPERATING SYSTEM</div><h2 class="h-xl">四项机制协同运转</h2></div>
    <div class="grid-4" style="margin-top:6vh;align-items:center">
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="cog"></i></div><div class="card-title">机制一</div><p class="card-body">输入、责任和节奏。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="refresh-cw"></i></div><div class="card-title">机制二</div><p class="card-body">流转、反馈和复盘。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="network"></i></div><div class="card-title">机制三</div><p class="card-body">协同、治理和对齐。</p></div>
      <div class="card" data-anim><div class="icon-disc"><i data-lucide="check-circle-2"></i></div><div class="card-title">机制四</div><p class="card-body">验收、沉淀和扩展。</p></div>
    </div>
  </div>
</section>
```

## H24 · Arrow Callout Timeline

长红箭头 + 多个信息框。适合搜索/漏斗/推进路径、政策流程、项目阶段复盘。

```html
<section class="slide" data-layout="H24" data-animate="arrow-timeline">
  <div class="chrome"><div class="l"><span class="square"></span><span>推进路径</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">PATH</div><h2 class="h-xl">从输入到结果的关键路径</h2></div>
    <div class="arrow-timeline" data-anim>
      <div class="arrow-timeline-line"></div>
      <div class="arrow-timeline-head"></div>
      <div class="card arrow-timeline-card top" style="left:6%;width:18vw"><div class="num-pill">01</div><p class="card-body">阶段说明</p></div>
      <div class="card arrow-timeline-card bottom" style="left:30%;width:18vw"><div class="num-pill">02</div><p class="card-body">阶段说明</p></div>
      <div class="card arrow-timeline-card top" style="left:54%;width:18vw"><div class="num-pill">03</div><p class="card-body">阶段说明</p></div>
    </div>
  </div>
</section>
```

## H25 · Photo Quote

整张照片 + 左侧红色标题块 / 引语块。适合会议、发布会、现场故事、客户证言。图片要真实、明亮、可识别主体。

```html
<section class="slide" data-layout="H25" data-animate="photo-quote">
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>
  <div class="image-frame" style="position:absolute;inset:0;padding:0;border:0;box-shadow:none"><img src="images/25-scene.jpg" alt="现场照片"></div>
  <div style="position:absolute;left:7vw;top:18vh;width:25vw;background:var(--brand-red);color:#fff;padding:4vh 3vw" data-anim>
    <div class="kicker" style="color:rgba(255,255,255,.78)">FIELD STORY</div>
    <h2 class="h-md" style="margin-top:2vh">一句强结论覆盖照片现场</h2>
    <p style="margin-top:2vh;line-height:1.7">用于引用客户反馈、现场故事或发布会主题。</p>
  </div>
</section>
```

## H26 · Metaphor Compare

植物成长、双塔对比、金字塔等隐喻页。适合战略解释、方案对比、成长模型。只在需要“记忆点”时用,不要每页都用隐喻。

```html
<section class="slide" data-layout="H26" data-animate="metaphor">
  <div class="chrome"><div class="l"><span class="square"></span><span>方案对比</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">CONTRAST</div><h2 class="h-xl">两种路径的差异</h2></div>
    <div class="grid-2" style="margin-top:5vh;align-items:end">
      <div class="card" data-anim style="text-align:center"><div style="height:28vh;display:flex;align-items:end;justify-content:center;gap:.6vw"><span style="height:36%;width:3vw;background:#dfe3e8"></span><span style="height:58%;width:3vw;background:#cfd5dd"></span><span style="height:82%;width:3vw;background:var(--brand-red)"></span></div><div class="card-title">路径 A</div><p class="card-body">优势、限制、适用场景。</p></div>
      <div class="card" data-anim style="text-align:center"><div style="height:28vh;display:flex;align-items:end;justify-content:center;gap:.6vw"><span style="height:82%;width:3vw;background:var(--brand-red)"></span><span style="height:58%;width:3vw;background:#cfd5dd"></span><span style="height:36%;width:3vw;background:#dfe3e8"></span></div><div class="card-title">路径 B</div><p class="card-body">优势、限制、适用场景。</p></div>
    </div>
  </div>
</section>
```

## H27 · Problem Overview

三列问题拆解。适合痛点概览、现状挑战、客户问题、调研发现。

```html
<section class="slide" data-layout="H27" data-animate="problem-overview">
  <div class="chrome"><div class="l"><span class="square"></span><span>问题概览</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">PROBLEM</div><h2 class="h-xl">三个问题定义当前局面</h2></div>
    <div class="grid-3" style="margin-top:6vh">
      <div class="card flat" data-anim><div class="num-pill">01</div><div class="card-title">问题一</div><p class="card-body">用 2-3 句话描述问题来源、影响对象和为什么现在必须解决。</p></div>
      <div class="card flat" data-anim><div class="num-pill">02</div><div class="card-title">问题二</div><p class="card-body">适合写用户痛点、流程瓶颈、市场供需断点或组织成本。</p></div>
      <div class="card flat" data-anim><div class="num-pill">03</div><div class="card-title">问题三</div><p class="card-body">最后一列给出趋势性矛盾,引出后续方案和商业机会。</p></div>
    </div>
  </div>
</section>
```

## H28 · Market Size Donut

市场规模圆环 / 饼图 + 左右解释。适合 TAM/SAM/SOM、目标客群、市场空间、份额结构。

```html
<section class="slide" data-layout="H28" data-animate="market-size">
  <div class="chrome"><div class="l"><span class="square"></span><span>市场规模</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div class="grid-12" style="padding-top:9vh;align-items:center">
    <div class="span-4 content-stack" data-anim>
      <div class="kicker">MARKET TARGET</div><h2 class="h-md">目标市场</h2>
      <p class="body-copy">定义用户、行业、地域或场景边界,说明为什么这是当前最值得进入的市场。</p>
    </div>
    <div class="span-4" data-anim style="display:grid;place-items:center">
      <div style="width:20vw;height:20vw;border-radius:999px;background:conic-gradient(var(--brand-red) 0 65%,#dfe3e8 65% 100%);display:grid;place-items:center;box-shadow:var(--shadow-soft)">
        <div style="width:11vw;height:11vw;border-radius:999px;background:#fff;display:grid;place-items:center;text-align:center"><div class="stat-big" style="font-size:3vw">65%</div><p class="card-body">share / segment</p></div>
      </div>
    </div>
    <div class="span-4 content-stack" data-anim>
      <div class="kicker">MARKET POTENTIAL</div><h2 class="h-md">增长潜力</h2>
      <p class="body-copy">放入市场规模、增长率、渗透率或替代空间,并说明机会为什么不是短期噪音。</p>
    </div>
  </div>
</section>
```

## H29 · Funding Use Donut

资金用途 / 预算结构圆环。适合融资计划、预算分配、资源投入、成本结构。

```html
<section class="slide" data-layout="H29" data-animate="funding-use">
  <div class="chrome"><div class="l"><span class="square"></span><span>资金用途</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div class="grid-12" style="padding-top:9vh;align-items:center">
    <div class="span-5" data-anim style="display:grid;place-items:center">
      <div style="width:22vw;height:22vw;border-radius:999px;background:conic-gradient(var(--brand-red) 0 42%,#ef7b80 42% 58%,var(--brand-red-dark) 58% 89%,#dfe3e8 89% 100%);display:grid;place-items:center;box-shadow:var(--shadow-soft)">
        <div style="width:10vw;height:10vw;border-radius:999px;background:#fff;display:grid;place-items:center"><div class="stat-big" style="font-size:3vw">100%</div></div>
      </div>
    </div>
    <div class="span-7 grid-2" data-anim>
      <div class="card flat"><div class="card-title">42% 产品研发</div><p class="card-body">核心产品、平台能力、工程化和质量验证。</p></div>
      <div class="card flat"><div class="card-title">31% 市场获客</div><p class="card-body">销售渠道、品牌、活动和客户成功。</p></div>
      <div class="card flat"><div class="card-title">16% 团队建设</div><p class="card-body">关键岗位招聘、培训和组织能力建设。</p></div>
      <div class="card flat"><div class="card-title">11% 运营储备</div><p class="card-body">基础设施、法务、财务和不可预见支出。</p></div>
    </div>
  </div>
</section>
```

## H30 · Mini Market Share Charts

三组小柱状图并列。适合市场份额、竞品对比、区域表现、渠道拆分。

```html
<section class="slide" data-layout="H30" data-animate="market-share">
  <div class="chrome"><div class="l"><span class="square"></span><span>市场份额</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">COMPETITIVE SHARE</div><h2 class="h-xl">关键细分市场的份额变化</h2></div>
    <div class="grid-3" style="margin-top:5vh">
      <div class="card flat" data-anim><div class="card-title">Category One <span style="color:var(--brand-red)">45%</span></div><div style="height:24vh;display:flex;align-items:end;gap:.7vw"><span style="height:42%;width:2vw;background:#dfe3e8"></span><span style="height:55%;width:2vw;background:#cfd5dd"></span><span style="height:78%;width:2vw;background:var(--brand-red)"></span><span style="height:62%;width:2vw;background:#dfe3e8"></span></div></div>
      <div class="card flat" data-anim><div class="card-title">Category Two <span style="color:var(--brand-red)">22%</span></div><div style="height:24vh;display:flex;align-items:end;gap:.7vw"><span style="height:70%;width:2vw;background:#dfe3e8"></span><span style="height:36%;width:2vw;background:#cfd5dd"></span><span style="height:48%;width:2vw;background:var(--brand-red)"></span><span style="height:62%;width:2vw;background:#dfe3e8"></span></div></div>
      <div class="card flat" data-anim><div class="card-title">Competitor Gap <span style="color:var(--brand-red)">33%</span></div><div style="height:24vh;display:flex;align-items:end;gap:.7vw"><span style="height:32%;width:2vw;background:#dfe3e8"></span><span style="height:46%;width:2vw;background:#cfd5dd"></span><span style="height:73%;width:2vw;background:var(--brand-red)"></span><span style="height:58%;width:2vw;background:#dfe3e8"></span></div></div>
    </div>
  </div>
</section>
```

## H31 · Business Model Cards

商业模式 / 产品入口卡片。适合 app、平台、渠道、收入模型,可放 2-4 张产品图或示意卡。

```html
<section class="slide" data-layout="H31" data-animate="business-model">
  <div class="chrome"><div class="l"><span class="square"></span><span>商业模式</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">BUSINESS MODEL</div><h2 class="h-xl">产品、渠道和收入模型如何闭合</h2></div>
    <div class="grid-4" style="margin-top:5vh">
      <div class="card" data-anim style="background:var(--brand-red);color:#fff"><div class="icon-disc" style="background:#fff;color:var(--brand-red)"><i data-lucide="download"></i></div><div class="card-title" style="color:#fff">入口一</div><p style="line-height:1.6">核心获客入口和转化动作。</p></div>
      <div class="image-frame r-4x3" data-anim><img src="images/31-model-01.jpg" alt="商业模式图片 1"></div>
      <div class="card" data-anim style="background:var(--brand-red-dark);color:#fff"><div class="icon-disc" style="background:#fff;color:var(--brand-red)"><i data-lucide="upload"></i></div><div class="card-title" style="color:#fff">入口二</div><p style="line-height:1.6">留存、复购或增值服务路径。</p></div>
      <div class="image-frame r-4x3" data-anim><img src="images/31-model-02.jpg" alt="商业模式图片 2"></div>
    </div>
  </div>
</section>
```

## H32 · KPI Square Loop

四个 KPI 方块 + 循环箭头。适合增长闭环、转化漏斗、运营指标、关键数字页。

```html
<section class="slide" data-layout="H32" data-animate="kpi-loop">
  <div class="chrome"><div class="l"><span class="square"></span><span>关键数字</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div class="grid-12" style="padding-top:9vh;align-items:center">
    <div class="span-4 content-stack" data-anim><div class="kicker">LOOK AT NUMBERS</div><h2 class="h-md">四个指标构成增长闭环</h2><p class="body-copy">用循环箭头表达指标之间互相驱动,适合把运营数字讲成一套机制。</p></div>
    <div class="span-8" data-anim style="position:relative;height:50vh">
      <div class="card flat" style="position:absolute;left:22%;top:5%;width:13vw;text-align:center;background:var(--brand-red);color:#fff"><div class="stat-big" style="font-size:3vw;color:#fff">85%</div><p>Metric One</p></div>
      <div class="card flat" style="position:absolute;right:22%;top:5%;width:13vw;text-align:center;background:#dfe3e8"><div class="stat-big" style="font-size:3vw">92%</div><p>Metric Two</p></div>
      <div class="card flat" style="position:absolute;left:22%;bottom:5%;width:13vw;text-align:center;background:#dfe3e8"><div class="stat-big" style="font-size:3vw">72%</div><p>Metric Three</p></div>
      <div class="card flat" style="position:absolute;right:22%;bottom:5%;width:13vw;text-align:center;background:var(--brand-red);color:#fff"><div class="stat-big" style="font-size:3vw;color:#fff">95%</div><p>Metric Four</p></div>
      <div style="position:absolute;left:42%;top:49%;width:12vw;height:1px;background:var(--line-strong)"></div>
      <div style="position:absolute;left:49%;top:30%;width:1px;height:16vh;background:var(--line-strong)"></div>
    </div>
  </div>
</section>
```

## H33 · Pricing Table

价格表 / 套餐表。适合 SaaS 定价、服务包、咨询报价、版本权益对比。

```html
<section class="slide" data-layout="H33" data-animate="pricing-table">
  <div class="chrome"><div class="l"><span class="square"></span><span>定价方案</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">PRICING PLAN</div><h2 class="h-xl">四档套餐覆盖不同客户成熟度</h2></div>
    <div class="grid-4" style="margin-top:5vh">
      <div class="card flat" data-anim><div class="card-title">Basic</div><div class="stat-big" style="font-size:2.4vw">$35</div><p class="card-body">入门功能、基础支持、月度报告。</p></div>
      <div class="card flat" data-anim><div class="card-title">Lite</div><div class="stat-big" style="font-size:2.4vw">$50</div><p class="card-body">团队协作、自动化流程、标准集成。</p></div>
      <div class="card flat" data-anim style="border-color:var(--brand-red)"><div class="card-title">Business</div><div class="stat-big" style="font-size:2.4vw">$80</div><p class="card-body">高级治理、审计、权限和客户成功。</p></div>
      <div class="card flat" data-anim><div class="card-title">Enterprise</div><div class="stat-big" style="font-size:2.4vw">Custom</div><p class="card-body">私有化、SLA、专属实施和安全评估。</p></div>
    </div>
  </div>
</section>
```

## H34 · SWOT Dark Panel

深色 SWOT 分析。适合机会风险、竞争格局、战略判断、产品强弱势。

```html
<section class="slide dark" data-layout="H34" data-animate="swot">
  <div class="chrome"><div class="l"><span class="square"></span><span>SWOT</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">PRODUCT STRENGTH</div><h2 class="h-xl">优势、弱点、机会和威胁</h2></div>
    <div class="grid-4" style="margin-top:6vh">
      <div class="card flat" data-anim style="background:rgba(255,255,255,.10);color:#fff"><div class="card-title" style="color:#fff">S / Strength</div><p style="line-height:1.6">核心优势和可持续差异。</p></div>
      <div class="card flat" data-anim style="background:rgba(255,255,255,.10);color:#fff"><div class="card-title" style="color:#fff">W / Weakness</div><p style="line-height:1.6">短板、依赖和执行风险。</p></div>
      <div class="card flat" data-anim style="background:rgba(255,255,255,.10);color:#fff"><div class="card-title" style="color:#fff">O / Opportunity</div><p style="line-height:1.6">市场窗口和外部机会。</p></div>
      <div class="card flat" data-anim style="background:rgba(255,255,255,.10);color:#fff"><div class="card-title" style="color:#fff">T / Threat</div><p style="line-height:1.6">竞争、替代和监管压力。</p></div>
    </div>
  </div>
</section>
```

## H35 · Gantt Milestones

甘特图 / 项目里程碑。适合项目计划、产品路线、季度推进、实施排期。

```html
<section class="slide" data-layout="H35" data-animate="gantt">
  <div class="chrome"><div class="l"><span class="square"></span><span>里程碑</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">TIMELINES AND MILESTONES</div><h2 class="h-xl">季度推进计划</h2></div>
    <div class="card flat" style="margin-top:5vh" data-anim>
      <div style="display:grid;grid-template-columns:7vw repeat(6,1fr);gap:.7vw;align-items:center">
        <div></div><div class="meta">JAN</div><div class="meta">FEB</div><div class="meta">MAR</div><div class="meta">APR</div><div class="meta">MAY</div><div class="meta">JUN</div>
        <div class="card-title">Research</div><div style="grid-column:2 / 4;background:#dfe3e8;padding:1vh">调研</div><div style="grid-column:4 / 5;background:var(--brand-red);color:#fff;padding:1vh">评审</div><div></div><div></div>
        <div class="card-title">Build</div><div></div><div style="grid-column:3 / 6;background:#cfd5dd;padding:1vh">开发</div><div style="grid-column:6 / 7;background:var(--brand-red);color:#fff;padding:1vh">发布</div>
        <div class="card-title">Launch</div><div></div><div></div><div style="grid-column:4 / 7;background:#dfe3e8;padding:1vh">推广与复盘</div>
      </div>
    </div>
  </div>
</section>
```

## H36 · Client Testimonials

客户证言 / 人物反馈。适合用户评价、合作伙伴背书、团队反馈、专家观点。

```html
<section class="slide" data-layout="H36" data-animate="testimonials">
  <div class="chrome"><div class="l"><span class="square"></span><span>客户证言</span></div><div></div></div>
  <div class="brand-lockup"><span class="brand-mark" aria-hidden="true"></span><span>HUAWEI</span></div>

  <div style="padding-top:8vh">
    <div class="content-stack" data-anim><div class="kicker">CLIENT TESTIMONIALS</div><h2 class="h-xl">来自关键客户的反馈</h2></div>
    <div class="grid-3" style="margin-top:6vh">
      <div class="card flat" data-anim style="text-align:center"><div style="font-size:4vw;color:var(--brand-red)">“</div><p class="card-body">一句真实、有指向性的客户反馈,说明产品解决了什么问题。</p><div class="num-pill" style="margin-top:2vh">A</div><div class="card-title">Name</div></div>
      <div class="card flat" data-anim style="text-align:center"><div style="font-size:4vw;color:var(--brand-red)">“</div><p class="card-body">可以写行业、职位、使用场景,避免空泛赞美。</p><div class="num-pill" style="margin-top:2vh">B</div><div class="card-title">Name</div></div>
      <div class="card flat" data-anim style="text-align:center"><div style="font-size:4vw;color:var(--brand-red)">“</div><p class="card-body">最后一条用于强化转化、效率、收入或风险降低。</p><div class="num-pill" style="margin-top:2vh">C</div><div class="card-title">Name</div></div>
    </div>
  </div>
</section>
```

## 选版式决策表

| 你要表达 | 选 |
|---|---|
| 首页、主题、汇报人 | H01 |
| 目录 / 章节索引 | H02 |
| 新章节开始 | H03 |
| 背景、前言、说明文字 | H04 |
| 三个能力 / 三项策略 | H05 |
| 年度进展 / 里程碑 | H06 |
| 指标、达成率、横向数据对比 | H07 |
| 流程、路径、方法论 | H08 |
| 照片、产品图、案例证据 | H09 |
| 结束页 | H10 |
| 前言、背景长说明、研究口径 | H11 |
| 案例摘要、新闻式图文、会议纪要 | H12 / H25 |
| 多图横向陈列、活动回顾 | H13 |
| 团队、专家、人物阵容 | H14 |
| 大数字、KPI 看板、年度结果 | H15 |
| 趋势、柱线组合、经营分析 | H16 / H22 |
| 能力模型、生态关系、中心辐射 | H17 |
| 路线图、阶段推进、成熟度路径 | H18 / H24 |
| 客户案例、区域项目、圆形照片集 | H19 |
| 图标化能力清单、产品模块 | H20 |
| 地图、区域布局、网点分布 | H21 |
| 协同机制、闭环流程、齿轮关系 | H23 |
| 战略隐喻、双路径对比、成长模型 | H26 |
| 问题概览、市场规模、融资用途 | H27 / H28 / H29 |
| 市场份额、商业模式、KPI 闭环 | H30 / H31 / H32 |
| 定价、SWOT、甘特计划、客户证言 | H33 / H34 / H35 / H36 |

## 常犯错误

- 不要把页面做得过度互联网化:大圆角、渐变按钮、彩色卡片会破坏企业汇报感。
- 不要在每页都放大 logo;右上品牌位已经足够。
- 不要给同一页放太多红色圆形图标;每页 3-5 个就够。
- 不要把正文塞满;Huawei 企业汇报的信息密度可以偏高,但网页 PPT 大屏展示仍要留白。
- 不要在图片页混用不同宽高比。
- 不要把目录页、章节页、正文页都做成同一版式;红色大块只适合封面、目录、章节和结尾。
