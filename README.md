<!-- Repository Header Begin -->
<div align="center">
<img src="https://puni.sh/_next/image?url=https%3A%2F%2Fs3.puni.sh%2Fmedia%2Fplugin%2F7%2Ficon-bl3wub19h2u.png&w=256&q=100" alt="Saucy IconUrl" width="15%">

# Saucy

Automates certain Gold Saucer mini-games.

</div>

<div align="left">
<h4>Currently supports:</h1>
<ul>
<li>Cuff-a-cur</li>
<li>Triple Triad</li>
<li>Out on a Limb</li>
<li>Slice is Right</li>
<li>Auto Cactpot</li>
<li>Air Force One</li>

Tracks Stats for Lifetime, Sessions, Hourly MGP and more!

Localized in English and 简体中文 (Simplified Chinese). The UI follows the Dalamud language by default and can be switched from the sidebar's language selector.

<!-- Repository Header End -->

---

## 关于这个 Fork

这是 `blackappleD` 维护的国服分支，Fork 自 [PunishXIV/Saucy](https://github.com/PunishXIV/Saucy)。
相比上游只有两点差别：完整的简体中文本地化，以及独立的插件标识 `saucy-bld`（因此可以和官方版同时安装，配置互不干扰）。
游戏逻辑没有改动。

通过自建卫月仓库安装：

```text
https://raw.githubusercontent.com/blackappleD/DalamudPlugins/main/repo.json
```

> 注意：本分支与官方 Saucy 使用同一个 `/saucy` 命令。两者同时启用时该命令会冲突，建议只启用其中一个。

### 同步上游更新

Fork 关系保留完整，上游更新可以直接合并：

```bash
git fetch upstream
git merge upstream/master
```

改名只动了 `Saucy.csproj` 中的 `<AssemblyName>` 和清单文件名（`Saucy.json` → `saucy-bld.json`），
工程路径、`namespace Saucy` 和各类型名都保持原样，所以上游合并基本不会产生冲突。
合并后请确认 `<None Update="saucy-bld.json">` 仍在 `Saucy.csproj` 中——如果上游改动了那一行，需要手工改回来。

### 版本号规则

沿用上游版本号的前三段，第四段作为本分支的修订号，从 `2001` 起递增：上游 `2.1.2.x` 对应本分支 `2.1.2.2001`。
这样本分支始终高于同代上游版本，又低于上游的下一代（`2.1.3`）。合并上游新版本后，把前三段跟上去、第四段重新从 `2001` 起算。
每次发布必须严格递增，且与 `repo.json` 中的 `AssemblyVersion` 一致。

### 许可与致谢

代码版权归原作者所有（BSD 3-Clause，见 [LICENCE.md](LICENCE.md)），本分支只做本地化和打包维护。
本分支的问题请在本仓库反馈，不要占用上游的 issue 和 Puni.sh 的支持频道。

