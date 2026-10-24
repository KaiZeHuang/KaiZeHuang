<h1 align="center">KaiZeHuang</h1>

<p align="center">
  <strong>Android 平台开发 · 构建体系 · 原生层</strong><br>
  <sub>Android platform work — Gradle build logic, JNI and native probes, Compose UI, and the tooling that keeps a multi-module codebase honest.</sub>
</p>

<p align="center">
  <a href="https://github.com/KaiZeHuang/vernier"><img src="https://img.shields.io/badge/-Vernier-0F1115?style=flat-square&logo=android&logoColor=3DDC84" alt="Vernier"></a>
  <img src="https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white" alt="Kotlin">
  <img src="https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white" alt="C/C++">
  <img src="https://komarev.com/ghpvc/?username=KaiZeHuang&style=flat-square&color=0F1115" alt="Profile views">
</p>

---

### flagship project · 主力项目

## [Vernier](https://github.com/KaiZeHuang/vernier)

一个在设备本机运行的 Android 环境完整性检测应用。17 个探测器覆盖引导状态、root 与 SU 痕迹、运行时注入、挂载命名空间、系统属性、可疑应用、KeyStore 与 attestation 一致性，以及虚拟化迹象。

An on-device Android environment integrity inspector. Seventeen detectors cover boot state, root and SU artifacts, runtime injection, mount namespace anomalies, modified system properties, suspicious applications, KeyStore and attestation consistency, and signs of virtualization.

| | |
| :--- | :--- |
| **Stack** | Kotlin · Jetpack Compose · C++ / assembly (JNI) · Gradle KTS |
| **Shape** | `core` / `capability` / `sdk` / `feature` / `app` — 多模块，边界由 CI 强制 |
| **Detectors** | 17 个，每个自带 domain / data / presentation / detector / ui 五层 |
| **SDK** | 同一套探测器同时以无 UI 的 AAR 发布，可嵌入其他应用 |
| **Platform** | minSdk 29 · targetSdk 37 · arm64-v8a / armeabi-v7a / x86 / x86_64 |

它有意思的地方不在探测器本身，而在约束：

- **模块边界写进 CI，不靠约定** — 模块边界、原生边界、JNI 契约、反射白名单、文本协议、证据记录、文件长度，7 个守卫脚本在每次 push 时执行。
- **同一探测器，两种出口** — app 的 Compose 界面和 SDK AAR 共用同一个探测器目录，不存在两份实现。
- **证据而非结论** — 每张卡片说明它看到了什么、为什么这算证据、以及它看不到什么。

<p align="center">
  <a href="https://github.com/KaiZeHuang/vernier"><img src="https://img.shields.io/badge/-Repository-0F1115?style=flat-square&logo=github&logoColor=white" alt="Repository"></a>
  <a href="https://github.com/KaiZeHuang/vernier/releases"><img src="https://img.shields.io/badge/-Releases-0F1115?style=flat-square&logo=githubactions&logoColor=white" alt="Releases"></a>
  <a href="https://github.com/KaiZeHuang/vernier/blob/main/SECURITY.md"><img src="https://img.shields.io/badge/-Security%20Policy-0F1115?style=flat-square&logo=shield&logoColor=white" alt="Security policy"></a>
</p>

---

### 我关心的 / What I care about

- **能跑通的结构**，而不是画上去的结构。模块边界写进 CI，文档跟着代码走。
- **原生层的诚实**。JNI 边界、符号可见性、探针在哪些 ABI 上真的有结果，都写清楚。
- **可复现的构建**。版本号从 git 元数据推导，缓存和并发有明确策略，取消构建不会留下锁。
- **中英双语**。界面和文档都不只做一半。

---

<p align="center">
  <sub>Vernier 相关问题请到对应仓库开 issue 或 discussion；安全问题请看 SECURITY.md。</sub><br>
  <sub>Questions about Vernier go to that repository's issues or discussions. Security reports go through its SECURITY.md.</sub>
</p>
