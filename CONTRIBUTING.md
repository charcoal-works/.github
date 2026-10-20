# Contributing

[English](#english) · [简体中文](#简体中文)

---

## English

Thanks for helping. This guide applies to every repository under Charcoal Works.
By participating, you agree to follow the
[Code of Conduct](CODE_OF_CONDUCT.md).

### Repositories

| Repository | Stack | Notes |
| --- | --- | --- |
| `charcoal-ipa` | Swift 6 / SwiftUI + embedded Node 24 engine | Fork of [Pastel](https://github.com/EEliberto/Pastel-macOS) |
| `charcoal-apk` | TypeScript / Electron + Rust sidecar | In design |
| `.github` | Markdown / YAML | Organization profile and templates |

### Development (Charcoal IPA)

Requirements:

- macOS 26 or later, Apple silicon
- Xcode 26 or later (beta is fine)
- Node.js 24 (release builds use the bundled runtime)

```bash
cd NodeProject
npm install
npm test
cd ..
open Pastel.xcodeproj
```

Command-line build:

```bash
xcodebuild -project Pastel.xcodeproj \
  -scheme Pastel \
  -configuration Debug \
  -derivedDataPath "$TMPDIR/CharcoalIPA-DerivedData" \
  build
```

Release packaging:

```bash
sh Scripts/BuildAdHocDMG.sh
```

> The Xcode project, target, and scheme are still named `Pastel`. See
> `charcoal-ipa/BRANDING.md` for the remaining rename work.

### Pull requests

1. Open an issue first for non-trivial changes.
2. Branch from `main`: `feat/...`, `fix/...`, `docs/...`, `chore/...`.
3. Keep commits focused and use the imperative mood
   (`Add version picker`, not `Added ...`).
4. Run the relevant build and tests before pushing.
5. Fill in the PR template, including what you tested.
6. CI must pass. A maintainer will review.

Do not include Apple ID / Google credentials, session tokens, Keychain exports,
private keys, certificates, provisioning profiles, signing material, downloaded
IPA/APK files, or build products (`dist/`, `DerivedData/`, `node_modules/`).

**Never publish a secret.** Private keys, signing identities, API tokens, and
account credentials stay out of code, docs, issues, and pull requests. Use
GitHub Actions secrets and environment protection for CI.

### Code style

- Swift: follow the existing structure and Swift 6 strict concurrency settings.
- TypeScript: keep modules small and typed; no `any` unless justified.
- Do not log credentials, tokens, or full request bodies.
- New user-visible strings must be added to `Localizable.xcstrings` (IPA) or the
  equivalent i18n catalog (APK).

### Security

Never report vulnerabilities in a public issue. See [SECURITY.md](SECURITY.md).

### Licensing

Contributions are accepted under the Apache License 2.0. There is no CLA;
submitting a pull request means you agree to license your contribution under the
same terms.

### Upstream policy (Charcoal IPA)

Charcoal IPA is a fork. Keep the upstream attribution and `NOTICE` intact, and
prefer small, reviewable patches so upstream fixes can be rebased cleanly.

```bash
git remote add upstream https://github.com/EEliberto/Pastel-macOS.git
git fetch upstream
git rebase upstream/main
```

After a rebase, re-check the brand-specific files listed in `BRANDING.md`.

---

## 简体中文

感谢参与。本指南适用于 Charcoal Works 下的所有仓库。参与即表示你同意遵守[行为准则](CODE_OF_CONDUCT.md)。

### 仓库

| 仓库 | 技术栈 | 说明 |
| --- | --- | --- |
| `charcoal-ipa` | Swift 6 / SwiftUI + 内置 Node 24 引擎 | 基于 [Pastel](https://github.com/EEliberto/Pastel-macOS) 的 fork |
| `charcoal-apk` | TypeScript / Electron + Rust sidecar | 设计中 |
| `.github` | Markdown / YAML | 组织主页与模板 |

### 开发环境（Charcoal IPA）

- macOS 26 或更高，Apple 芯片
- Xcode 26 或更高（beta 版也可以）
- Node.js 24（发布构建使用仓库内置运行时）

```bash
cd NodeProject
npm install
npm test
cd ..
open Pastel.xcodeproj
```

命令行构建：

```bash
xcodebuild -project Pastel.xcodeproj \
  -scheme Pastel \
  -configuration Debug \
  -derivedDataPath "$TMPDIR/CharcoalIPA-DerivedData" \
  build
```

生成 DMG：

```bash
sh Scripts/BuildAdHocDMG.sh
```

> Xcode 工程、target 和 scheme 目前仍叫 `Pastel`，品牌重命名尚未完成，见 `charcoal-ipa/BRANDING.md`。

### 提交 Pull Request

1. 非简单改动请先开 issue 讨论。
2. 从 `main` 拉分支：`feat/...`、`fix/...`、`docs/...`、`chore/...`。
3. 提交信息用祈使句，保持单一主题：`Add version picker`，不要写 `Added ...`。
4. 推送前跑对应构建和测试。
5. 填写 PR 模板，写清你验证了什么。
6. CI 必须通过，然后等待维护者 review。

**不要提交**：Apple ID / Google 凭据、会话 token、Keychain 导出、私钥、证书、描述文件、签名材料、下载的 IPA/APK、构建产物（`dist/`、`DerivedData/`、`node_modules/`）。

**任何保密信息都不要写出来。** 私钥、签名身份、API token 和账号凭据不得出现在代码、文档、issue 或 PR 中。CI 使用 GitHub Actions secrets 和环境保护规则。

### 代码风格

- Swift：遵循现有结构与 Swift 6 严格并发设置。
- TypeScript：模块尽量小、类型完整；避免无理由的 `any`。
- 不记录凭据、token 或完整请求体。
- 新增用户可见文案必须加入 `Localizable.xcstrings`（IPA）或对应的 i18n 文件（APK）。

### 安全

不要在公开 issue 里报告漏洞，见 [SECURITY.md](SECURITY.md)。

### 许可

贡献按 Apache License 2.0 接受。没有 CLA；提交 PR 即表示你同意以相同许可证授权你的贡献。

### 上游同步（Charcoal IPA）

Charcoal IPA 是 fork。请保留上游署名和 `NOTICE`，并尽量保持补丁小而可 review，方便 rebase。

```bash
git remote add upstream https://github.com/EEliberto/Pastel-macOS.git
git fetch upstream
git rebase upstream/main
```

rebase 后按 `BRANDING.md` 重新检查品牌相关文件。
