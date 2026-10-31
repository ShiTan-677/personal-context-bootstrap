# personal-context bootstrap

我的个人偏好、项目目录与设备约定存在一个**私有**仓库 `ShiTan-677/personal-context` 里，跨设备、跨 Agent 环境共享。

这个公开仓库只解决一件事：**一台新电脑在拿到那个私有仓库之前，要先做什么。**

## 顺序

1. **安装 Git。**

2. **完成 GitHub 认证。** 有 GitHub CLI 时最省事：

   ```bash
   gh auth login
   gh auth setup-git
   ```

3. **把私有仓库克隆到用户目录。**

   Windows（PowerShell）：

   ```powershell
   git clone https://github.com/ShiTan-677/personal-context.git $env:USERPROFILE\personal-context
   ```

   macOS / Linux：

   ```bash
   git clone https://github.com/ShiTan-677/personal-context.git ~/personal-context
   ```

4. **打开 `INDEX.md`**，按里面的主题表按需读取；不确定从哪进就先看 `START_HERE.md`。

5. **再进入其他工具**（DeepSeek Harness、Codex 等）的首次会话。

## 为什么认证必须早于克隆

目标仓库是私有的。没有认证，第 3 步会直接卡在权限错误上；而"该怎么认证"的说明本身在那个仓库里——入口在门内。

这就是为什么第一次接入必须由人做第 1、2 步：任何 Agent 都没有你的 GitHub 凭据，它无法替你完成克隆。

## 边界

- 这里不复制私有仓库的任何内容，只记录顺序。
- 凭据、Cookie、令牌不进入任何仓库；换机重新认证，不复制。
- 第 5 步的先后不影响正确性，但**首次 Agent 会话必须在克隆之后**，否则 Agent 读不到索引，等于没有上下文。
