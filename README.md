<h1 align="center">KaiZeHuang</h1>

<p align="center">
  <strong>Android 平台开发 · 构建体系 · 原生层</strong><br>
  <sub>Android platform work — Gradle build logic, JNI and native probes, Compose UI, and the tooling that keeps a multi-module codebase honest.</sub>
</p>

<p align="center">
  <a href="https://github.com/KaiZeHuang/vernier"><img src="https://img.shields.io/badge/-Vernier-0F1115?style=flat-square&logo=android&logoColor=3DDC84" alt="Vernier"></a>
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin">
  <img src="https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white" alt="C/C++">
  <img src="https://img.shields.io/badge/Shell-4EAA25?style=flat-square&logo=gnubash&logoColor=white" alt="Shell">
  <img src="https://komarev.com/ghpvc/?username=KaiZeHuang&style=flat-square&color=0F1115" alt="Profile views">
</p>

---

### 现在在做 / Currently

**[Vernier](https://github.com/KaiZeHuang/vernier)** — 一个在设备本机运行的 Android 环境完整性检测应用。17 个探测器覆盖引导状态、root 与 SU 痕迹、运行时注入、挂载命名空间、系统属性、可疑应用、KeyStore 与 attestation 一致性，以及虚拟化迹象。

An on-device Android environment integrity inspector. Seventeen detectors cover boot state, root and SU artifacts, runtime injection, mount namespace anomalies, modified system properties, suspicious applications, KeyStore and attestation consistency, and signs of virtualization.

它有意思的地方不在探测器本身，而在约束：

- **多模块 + CI 强制边界**：`core` / `capability` / `sdk` / `feature` / `app` 分层，模块边界、原生边界、JNI 契约、反射白名单、文本协议由 7 个守卫脚本在 CI 里执行，而不是靠约定。
- **同一探测器，两种出口**：app 的 Compose 界面和一个无 UI 的 SDK AAR 共用同一个探测器目录。
- **证据而非结论**：每张卡片说明它看到了什么、为什么这算证据、以及它看不到什么。

---

### 项目 / Repositories

| | |
| :--- | :--- |
| **[Vernier](https://github.com/KaiZeHuang/vernier)** | Android 环境完整性检测 · Kotlin + 原生探针 + Compose，多模块，CI 强制边界 |
| **[solana-auditor-skill](https://github.com/KaiZeHuang/solana-auditor-skill)** | Solana AI Kit 的生产级安全审计技能 |
| **[position-manager-skill](https://github.com/KaiZeHuang/position-manager-skill)** | 仓位管理技能 |

---

### 我关心的 / What I care about

- **能跑通的结构**，而不是画上去的结构。模块边界写进 CI，文档跟着代码走。
- **原生层的诚实**。JNI 边界、符号可见性、探针在哪些 ABI 上真的有结果，都写清楚。
- **可复现的构建**。版本号从 git 元数据推导，缓存和并发有明确策略，取消构建不会留下锁。
- **中英双语**。界面和文档都不只做一半。

---

<p align="center">
  <sub>有问题就去对应仓库开 issue 或 discussion；安全问题请看各仓库的 SECURITY.md。</sub><br>
  <sub>Questions go to the repository's issues or discussions. Security reports go through SECURITY.md.</sub>
</p>
