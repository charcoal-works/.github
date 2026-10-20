# Security Policy

[English](#english) · [简体中文](#简体中文)

---

## English

### Supported versions

| Version | Supported |
| --- | --- |
| 1.x | ✅ |
| < 1.0 | ❌ |

### Reporting a vulnerability

**Please do not open a public issue for security problems.**

Use GitHub's private vulnerability reporting:

- Open the affected repository's **Security** tab → **Report a vulnerability**
- Or email `security@charcoal-works.com`

Include, when possible:

- Affected product and version
- macOS / Windows version and architecture
- A minimal reproduction
- Impact assessment
- Any suggested fix

**Never include Apple ID or Google account passwords, 2FA codes, session
tokens, or downloaded account data.** Redact logs before sending.

### Secrets

Never commit or publish private keys, certificates, provisioning profiles,
signing identities, API tokens, or account credentials. CI secrets belong in
GitHub Actions secrets with environment protection, never in workflow files.

If a secret is exposed, rotate it first, then contact
`security@charcoal-works.com`.

### What to expect

- Acknowledgement within **3 business days**
- Triage and severity assessment within **7 business days**
- A coordinated disclosure date once a fix is available
- Credit in the advisory, unless you prefer to stay anonymous

### Scope

In scope:

- Credential handling and local storage (Keychain, Credential Manager, session files)
- Update signing and delivery (Sparkle / electron-updater)
- Download integrity, path traversal, archive handling
- Privilege boundaries between the UI, the embedded engine, and sidecars
- Supply-chain issues in shipped dependencies

Out of scope:

- Apple or Google account restrictions resulting from normal use
- DRM, FairPlay, or paid-content bypass
- Vulnerabilities in upstream projects that we merely vendor, unless our
  integration makes them exploitable
- Social engineering or physical access

### Safe harbor

We will not pursue legal action for good-faith research that follows this
policy, avoids privacy violations and service disruption, and gives us a
reasonable window to fix the issue before publication.

---

## 简体中文

### 支持版本

| 版本 | 支持 |
| --- | --- |
| 1.x | ✅ |
| < 1.0 | ❌ |

### 报告漏洞

**请不要为安全问题开公开 issue。**

使用 GitHub 的私密漏洞报告：

- 进入受影响仓库的 **Security** 标签页 → **Report a vulnerability**
- 或发送邮件到 `security@charcoal-works.com`

请尽量包含：

- 受影响的产品和版本
- macOS / Windows 版本与架构
- 最小复现步骤
- 影响评估
- 建议的修复方式

**不要在报告中包含 Apple ID / Google 账号密码、双重验证码、会话 token 或下载的账号数据。** 发送前请先脱敏日志。

### 保密原则

不要在代码、文档、issue 或 PR 中提交或公开任何私钥、证书、描述文件、签名身份、
API token 或账号凭据。CI 密钥只放在 GitHub Actions secrets 中，并启用环境保护规则，
不要写进 workflow 文件。

如果密钥已经泄露，请先轮换，再联系 `security@charcoal-works.com`。

### 响应时间

- 3 个工作日内确认
- 7 个工作日内完成分级评估
- 修复可用后协调公开时间
- 在公告中署名（除非你希望匿名）

### 范围

在范围内：

- 凭据处理与本地存储（Keychain、Credential Manager、会话文件）
- 更新签名与更新分发（Sparkle / electron-updater）
- 下载完整性、路径穿越、压缩包处理
- UI、内置引擎与 sidecar 之间的权限边界
- 随包分发的依赖的供应链问题

不在范围内：

- 正常使用工具导致的 Apple / Google 账号限制
- DRM、FairPlay 或付费内容绕过
- 仅作为依赖引入的上游项目漏洞，除非我们的集成使其可被利用
- 社会工程或物理接触

### 安全港

对于遵循本政策、不侵犯隐私、不破坏服务、并在公开前给我们合理修复时间的善意研究，我们不会采取法律行动。
