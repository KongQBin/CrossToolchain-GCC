# 🚀 CrossToolchain-GCC

[![C++ Standard](https://img.shields.io/badge/C++-17-blue.svg)](https://isocpp.org/)
[![Compression](https://img.shields.io/badge/Format-.txz-orange.svg)](https://en.wikipedia.org/wiki/XZ_Utils)
[![Platform](https://img.shields.io/badge/Platform-Linux%20x64-lightgrey.svg)]()
[![License](https://img.shields.io/badge/License-GPLv3-green.svg)](https://www.gnu.org/licenses/gpl-3.0)

**CrossToolchain-GCC** 是一套专为**国产化信创平台**打造的高性能、标准化、全架构 C++17 交叉编译工具链矩阵。

本项目旨在解决底层系统移植与跨平台开发中常见的“环境配置繁琐”、“Glibc 版本冲突”以及“工具链臃肿”等痛点。所有工具链均经过深度优化（Stripped）与高比例压缩，具备极高的分发效率与开箱即用的体验。

> [!IMPORTANT]
> **此全架构工具链无需刻意挑选旧发行版（低GLIBC版本）系统进行部署，使用 Rocky 或 Ubuntu 最新或较新的发行版本即可。**

---

## ✨ 核心特性 (Key Features)

* **信创全架构覆盖**：支持 x86_64, AArch64, MIPS64el (龙芯旧版) 以及 LoongArch64 (新旧双世界 ABI)。
* **精准的 Glibc 对齐**：针对不同架构的发展历史，精心挑选并锁定最低兼容的 Glibc 版本（如 x86 锁定 2.12，AArch64 锁定 2.18），确保产出二进制在旧版 CentOS 6 到最新的统信 UOS / 麒麟 Kylin 上均能无缝运行。
* **极致轻量级分发**：彻底剥离（Strip）所有非必要的 DWARF 调试符号，并采用高强度的 LZMA2 (`.txz`) 算法压缩，将数百 MB 的工具链缩减至 **30MB ~ 50MB**，实现秒级下载与 CI/CD 流水线极速部署。
* **现代 C++ 支持**：全系基于 GCC 8.x 及以上版本构建（LoongArch NA 采用 GCC 15.x），完全支持 C++17 标准特性，若申威与龙芯旧世界工具链官方有升级，后续将全线进入C++20/23时带。

---

## 📦 支持矩阵与下载 (Support Matrix)

请在 [Releases](../../releases) 页面下载对应架构的工具链压缩包。

| 目标架构 | 核心特性 / 适用场景 | GCC 版本 | Glibc | 压缩包参考命名 |
| :--- | :--- | :--- | :--- | :--- |
| **x86_64** | **[高兼容底座]** 支持 `-m32` 编译 32 位程序 | 8.3.0 | 2.12 | `*x86_64*multilib.txz` |
| **AArch64** | **[稳健 ARM64]** 规避早期 2.17 风险，对齐国内外 OS 基线 | 8.5.0 | 2.18 | `*aarch64*.txz` |
| **MIPS64el** | **[经典存量支持]** 适配 3A5000 之前的早期龙芯设备 | 8.5.0 | 2.19 | `*mips64el*.txz` |
| **LoongArch64 (OA)**| **[旧世界 ABI]** 源于龙芯开源社区，适配旧版业务 | 8.3.0 | 2.28 | `*loongarch64_OA*.txz` |
| **LoongArch64 (NA)**| **[新世界 ABI]** 适配最新版统信/麒麟等新世界生态 | 15.2.0 | 2.38 | `*loongarch64_NA*.txz` |

> **⚠️ 特别说明 (Regarding SW64):**
> > 因受限于官方商业保密协议（NDA），本项目暂不提供针对申威（Shenwei）架构的公开构建版本。如需申威交叉编译环境，敬请主动与申威官方进行对接。

---

## ☕ 支持与赞助 (Sponsor)

予人方便，予己方便……

愿天下有勤人，终有卷[💵]数……

🙏🙏🙏🙏🙏🙏🙏🙏🙏🙏🙏🙏

<p align="center">
  <img src="https://github.com/KongQBin/KongQBin/raw/main/%E9%A5%AD%E7%9B%86.jpg" width="300" alt="饭盆">
</p>

**如需获取企业级服务，请在打赏时备注联系方式。**

💡 **赞助防风控小贴士**：
扫码打赏时，若时间充裕，有劳在打赏备注里随手填一句 **“CrossToolchain”** 或 **“开源工具赞助”**。
这不仅能让我准确收到您的专属心意，更重要的是能帮助系统识别这是正常的虚拟开源赞助，避免商户码触发大数据风控。非常感谢您的支持！

*(如果您赞助了 50 元及以上，欢迎在备注中留下您的 GitHub ID，我将在本项目后续的致谢名单中为您挂榜署名。)*
