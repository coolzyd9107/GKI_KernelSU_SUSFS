<div align="center">

# GKI KernelSU SUSFS

**自动化构建 GKI 内核 | 集成 KernelSU + SUSFS**

[![GitHub Release](https://img.shields.io/github/v/release/zzh20188/GKI_KernelSU_SUSFS?style=for-the-badge&logo=android&color=green)](https://github.com/zzh20188/GKI_KernelSU_SUSFS/releases)
[![Coolapk](https://img.shields.io/badge/Follow-Coolapk-3DDC84?style=flat-square&logo=android&logoColor=white)](http://www.coolapk.com/u/11253396)
[![KernelSU](https://img.shields.io/badge/KernelSU-Supported-green)](https://kernelsu.org/)
[![SUSFS](https://img.shields.io/badge/SUSFS-Integrated-orange)](https://gitlab.com/simonpunk/susfs4ksu)

[**English**](README-EN.md) | 简体中文

---

</div>

## 🚀 快速导航

<table>
<tr>
<td align="center" width="33%">

**📖 文档**

[GitHub Wiki](https://github.com/zzh20188/GKI_KernelSU_SUSFS/wiki)

</td>
<td align="center" width="33%">

**📥 下载**

[Releases](https://github.com/zzh20188/GKI_KernelSU_SUSFS/releases)

</td>
<td align="center" width="33%">

**📋 更新日志**

[CHANGELOG](doc/CHANGELOG.md)

</td>
</tr>
</table>

---

## ⚠️ 兼容性提醒

> **注意：** 目前不支持一加 ColorOS 14、15，刷入后可能需要清除数据开机。

---

## ✨ 特色版本

| 版本 | 说明 | 下载链接 |
|:---:|:---|:---:|
| **hymo+gki** | 集成 [hymo 挂载元模块](https://github.com/Anatdx/hymo)（仅支持 6.6） | [Release v2.0.0-r24](https://github.com/zzh20188/GKI_KernelSU_SUSFS/releases/tag/v2.0.0-r24) |
| **resukisu+gki** | 集成 [ReSukisu](https://github.com/ReSukiSU/ReSukiSU) | [Release v2.0.0-r26](https://github.com/zzh20188/GKI_KernelSU_SUSFS/releases/tag/v2.0.0-r26) |

> 💡 预构建版本已支持零宽修复补丁，也可使用 [Unicode零宽修复模块](https://t.me/real5ec1cff/268) (Xposed)

---

## 📚 文档与指南

详细说明请查阅 [**GitHub Wiki（中英双语）**](https://github.com/zzh20188/GKI_KernelSU_SUSFS/wiki)

Wiki 涵盖内容：
- 📥 下载与刷写指南
- 🔄 无限重启处理
- 🐛 BUG 反馈指引
- 💡 使用技巧 Tips
- 📱 KSU 管理器与 SUSFS 模块
- ⏰ 内核构建时间说明
- 🆘 紧急救援指南
- 📊 内核版本兼容性说明
- **🔧 [Fork 与自定义编译指南](https://github.com/zzh20188/GKI_KernelSU_SUSFS/wiki/Fork%E4%B8%8E%E8%87%AA%E5%AE%9A%E4%B9%89%E7%BC%96%E8%AF%91%E6%8C%87%E5%8D%97)** - 学习如何 Fork 仓库并编译自己的内核
- **🧩 [自定义构建新手指南](https://github.com/zzh20188/GKI_KernelSU_SUSFS/wiki/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%9E%84%E5%BB%BA%E6%96%B0%E6%89%8B%E6%8C%87%E5%8D%97)** - 面向新手的自定义构建模板
如何使用见以下视频

> - https://raw.githubusercontent.com/zzh20188/GKI_KernelSU_SUSFS/HEAD/assets/eg1.mp4
> - https://raw.githubusercontent.com/zzh20188/GKI_KernelSU_SUSFS/HEAD/assets/eg2.mp4

谷歌GKI发布地址：https://source.android.com/docs/core/architecture/kernel/gki-release-builds?hl=zh-cn

---

## 🔧 自定义提交配置

通过 [`config/config`](config/config) 文件可以指定 SUSFS 和 SukiSU 使用特定的 commit。

**什么是提交 (commit)？**

提交是一串哈希字符串，代表仓库在某个时间点的状态。例如将 sukisu 设为 `4b8644515fe6d87a109129e590ccd9d33a855dca`，即使用 1 月 30 日的 SukiSU 版本编译内核。

**为什么要指定提交？**

- 当上游仓库更新引入 bug 或兼容性问题时，可回退到稳定版本
- 当 SUSFS 与 SukiSU 版本不同步导致编译失败时，可手动指定兼容的版本

**如何获取提交哈希？**

- SUSFS: https://gitlab.com/simonpunk/susfs4ksu
- SukiSU: https://github.com/SukiSU-Ultra/SukiSU-Ultra

```ini
# 启用自定义提交
custom=true

# SUSFS 各分支的 commit hash
gki-android12-5.10=
gki-android13-5.15=
gki-android14-6.1=
gki-android15-6.6=

# SukiSU 的 commit hash
sukisu=
```

> 留空则使用该分支的最新提交。

---

## 🛠️ 安装后推荐

### 📦 模块推荐

<table>
<tr>
<th>模块名称</th>
<th>仓库</th>
<th>频道</th>
</tr>
<tr>
<td><b>LSPosed-Irena</b></td>
<td><a href="https://github.com/re-zero001/LSPosed-Irena">GitHub</a></td>
<td><a href="https://t.me/lsposed_irena">Telegram</a></td>
</tr>
<tr>
<td><b>Zygisk Next</b></td>
<td><a href="https://github.com/Dr-TSNG/ZygiskNext">GitHub</a></td>
<td rowspan="2"><a href="https://t.me/real5ec1cff">Telegram</a></td>
</tr>
<tr>
<td><b>TrickyStore</b></td>
<td><a href="https://github.com/5ec1cff/TrickyStore">GitHub</a></td>
</tr>
</table>

### 🔧 Xposed 模块

| 模块 | 说明 |
|:---:|:---|
| **FuseFixer** | [Unicode零宽修复模块](https://t.me/real5ec1cff/268) |

---

<div align="center">

**更多内容持续更新中...**

⭐ 如果这个项目对你有帮助，请点个 Star 支持一下！

</div>
