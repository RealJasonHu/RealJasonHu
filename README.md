<div align="center">
  <img src="./assets/profile-header.svg?v=3" width="100%" alt="Jason Hu — AI research and open-source engineering" />
</div>

<p align="center">
  <strong>I build tools that turn hard-to-debug failures into reproducible, inspectable evidence.</strong><br />
  <sub>把难以定位的问题，变成更小的复现案例、可执行测试与可审查的证据。</sub>
</p>

<p align="center">
  <a href="#selected-work">Selected work</a> ·
  <a href="#research">Research</a> ·
  <a href="#upstream-contributions">Upstream contributions</a> ·
  <a href="#engineering-approach">Engineering approach</a> ·
  <a href="https://github.com/RealJasonHu?tab=repositories">All repositories</a>
</p>

<p align="center">
  <img alt="Focus: AI reliability" src="https://img.shields.io/badge/AI-Reliability-74E2C0?style=flat-square&labelColor=0D1117" />
  <img alt="Focus: world models" src="https://img.shields.io/badge/World-Models-8CBFFF?style=flat-square&labelColor=0D1117" />
  <img alt="Focus: multimodal systems" src="https://img.shields.io/badge/Multimodal-Systems-C4B5FD?style=flat-square&labelColor=0D1117" />
  <img alt="Focus: developer tools" src="https://img.shields.io/badge/Developer-Tools-74E2C0?style=flat-square&labelColor=0D1117" />
</p>

<a id="selected-work"></a>
## Selected work / 原创项目

Three open-source tools, connected by one idea: **make a failure concrete enough to reproduce, inspect, and fix.** These are early-stage tools with documented boundaries, not claims of production maturity or general model accuracy.

### 01 / ReproCut — smaller journeys, the same bug

**Reduce a failing browser journey to a verified reproducer and a runnable regression test.**

ReproCut runs deletion experiments in fresh Chromium contexts and keeps a shorter action sequence only when the same declared failure still reproduces. It exports a replayable journey, a Playwright regression test, an offline evidence report, and a repair brief for a developer or coding agent.

<a href="https://github.com/RealJasonHu/reprocut">
  <img src="https://raw.githubusercontent.com/RealJasonHu/reprocut/main/docs/assets/demo-report.png" width="100%" alt="Actual ReproCut browser report showing a reduced journey and replay evidence" />
</a>

**Recorded demo: 12 → 3 actions · 36 browser replays · 75% fewer steps.** One deterministic fixture, not a cross-application benchmark. Verified reductions are single-deletion minimal under the observed replay conditions, not guaranteed globally shortest.

`JavaScript` `Node.js` `Playwright` `Delta debugging`

[Source & quick start](https://github.com/RealJasonHu/reprocut) · [Demo artifacts & releases](https://github.com/RealJasonHu/reprocut/releases/latest) · [中文介绍](https://github.com/RealJasonHu/reprocut/blob/main/README.zh-CN.md)

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>02 / <a href="https://github.com/RealJasonHu/renderwitness">RenderWitness</a></h3>
      <p><strong>Visual regression review, backed by inspectable evidence.</strong></p>
      <a href="https://github.com/RealJasonHu/renderwitness">
        <img src="https://raw.githubusercontent.com/RealJasonHu/renderwitness/main/docs/assets/workbench.png" width="100%" alt="Actual RenderWitness report from captured browser fixtures, using the offline metric-only provider" />
      </a>
      <p>Capture browser screenshots, isolate changed regions, and review the result with side-by-side, blend, and diff views.</p>
      <p>Includes scenario suites, ignore regions, explicit CI gates, and HTML / JSON / Markdown / JUnit exports. Optional VLM analysis stays separate from deterministic pixel evidence.</p>
      <p><sub>The illustrated demo is metric-only; it does not establish real-VLM accuracy. Alpha tool.</sub></p>
      <p><code>Python</code> <code>Playwright</code> <code>VLM adapters</code> <code>CI</code></p>
      <p><a href="https://github.com/RealJasonHu/renderwitness">Source &amp; demo</a> · <a href="https://github.com/RealJasonHu/renderwitness/blob/main/docs/ci.md">CI guide</a> · <a href="https://github.com/RealJasonHu/renderwitness/blob/main/README.zh-CN.md">中文</a></p>
    </td>
    <td width="50%" valign="top">
      <h3>03 / <a href="https://github.com/RealJasonHu/dreamfuzz">DreamFuzz</a></h3>
      <p><strong>Find, shrink, and replay world-model failures.</strong></p>
      <a href="https://github.com/RealJasonHu/dreamfuzz">
        <img src="https://raw.githubusercontent.com/RealJasonHu/dreamfuzz/main/docs/assets/hero.svg" width="100%" alt="DreamFuzz — property-based testing for world models" />
      </a>
      <p>Search for action sequences that expose model-vs-reference rollout drift, minimize the counterexample, and export a self-contained HTML replay.</p>
      <p>Uses explicit behavioral properties, paired open-loop rollouts, reproducible seeds, and an adapter contract for custom targets. The core has no third-party runtime dependencies.</p>
      <p><sub>Alpha diagnostic tool, not a model-training framework or a general evaluation leaderboard.</sub></p>
      <p><code>Python</code> <code>Property-based testing</code> <code>World models</code></p>
      <p><a href="https://github.com/RealJasonHu/dreamfuzz">Source</a> · <a href="https://realjasonhu.github.io/dreamfuzz/">Live replay</a> · <a href="https://github.com/RealJasonHu/dreamfuzz/blob/main/README.zh-CN.md">中文</a></p>
    </td>
  </tr>
</table>

<a id="research"></a>
## Research / 研究方向

I am interested in reliable multimodal systems, long-video understanding, and learning from limited supervision. My focus is on making model behavior testable, evidence traceable, and evaluation reproducible.

<sub>Public software is listed above. Research manuscripts, results, and code are linked only when cleared for public release.</sub>

<a id="upstream-contributions"></a>
## Upstream contributions / 开源协作

I also work on focused bug fixes, regression tests, documentation, and code review in existing projects. **Original projects, submitted patches, and review contributions are listed separately.**

### Merged

| Project | Contribution | Evidence |
| --- | --- | --- |
| **Podman Desktop** | Fixed navigation resize-handle layering beneath the welcome overlay, with a Playwright hit-test regression. | [Merged PR #18998](https://github.com/podman-desktop/podman-desktop/pull/18998) |

### Submitted pull requests

| Project | Contribution | Evidence |
| --- | --- | --- |
| **Instructor** | Preserve GenAI text-part metadata during templating, including thought signatures, without mutating caller-owned content. | [PR #2608](https://github.com/567-labs/instructor/pull/2608) |
| **Stable World Model** | Fix single-step iCEM planning so the existing horizon-one sampling path runs without an index error. | [PR #323](https://github.com/galilai-group/stable-worldmodel/pull/323) |
| **OpenPI** | Preserve histogram counts when normalization ranges expand, with regression coverage for quantile estimates. | [PR #1041](https://github.com/Physical-Intelligence/openpi/pull/1041) |
| **tqdm** | Fix notebook progress bars with CSS widths while preserving widget layout and numeric-width behavior. | [PR #1823](https://github.com/tqdm/tqdm/pull/1823) |
| **LiteLLM** | Preserve caller-provided spend metadata on authentication failures, with safe parsing and regression coverage. | [PR #38493](https://github.com/BerriAI/litellm/pull/38493) |
| **MuJoCo** | Clarify regularized-friction creep, the limits of <code>impratio</code>, and NoSlip tradeoffs in the documentation. | [PR #3526](https://github.com/google-deepmind/mujoco/pull/3526) |

<sub>Status checked on September 8, 2026: the six PRs above were open. The linked upstream threads are the source of truth for later changes.</sub>

### Code review

**LeRobot:** reviewed the intermediate-prediction contract for world-model policies and reported regression risks around evaluation flag propagation and non-image outputs entering the video path. [Review on PR #3757](https://github.com/huggingface/lerobot/pull/3757#pullrequestreview-5040741407).

<a id="engineering-approach"></a>
## Engineering approach / 工程取向

| Principle | What it looks like in the work |
| --- | --- |
| **A concrete failure before a broad claim** | A smaller browser journey, a model counterexample, or a numbered visual region—not just an aggregate score. |
| **Evidence separate from interpretation** | Deterministic measurements and replay artifacts remain inspectable; model recommendations carry explicit limits. |
| **Regression coverage with the fix** | Focused tests document the failure mode and guard the behavior being changed. |
| **Useful handoffs** | Runnable tests, structured JSON, portable reports, and documentation that another developer can use. |

## Toolbox / 工具箱

<p>
  <img alt="Python" src="https://img.shields.io/badge/Python-0D1117?style=flat-square&logo=python&logoColor=74E2C0" />
  <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-0D1117?style=flat-square&logo=javascript&logoColor=8CBFFF" />
  <img alt="Node.js" src="https://img.shields.io/badge/Node.js-0D1117?style=flat-square&logo=nodedotjs&logoColor=74E2C0" />
  <img alt="Playwright" src="https://img.shields.io/badge/Playwright-0D1117?style=flat-square" />
  <img alt="pytest" src="https://img.shields.io/badge/pytest-0D1117?style=flat-square&logo=pytest&logoColor=8CBFFF" />
  <img alt="GitHub Actions" src="https://img.shields.io/badge/GitHub_Actions-0D1117?style=flat-square&logo=githubactions&logoColor=C4B5FD" />
</p>

---

<p align="center">
  <strong>Jason Hu</strong><br />
  <sub>AI reliability · World models · Multimodal systems · Open source</sub>
</p>
