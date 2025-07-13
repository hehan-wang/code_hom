# Claude Code 接入指南

本项目为 Claude Code 命令行工具的接入与使用说明，支持直接在终端与 Claude 协作编程。

---

## 快速开始

### 1. 安装 Node.js (需版本 ≥ 18.0)

- **Ubuntu/Debian**
  ```bash
  curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo bash -
  sudo apt-get install -y nodejs
  node --version
  ```
- **macOS**
  ```bash
  sudo xcode-select --install
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  brew install node
  node --version
  ```

### 2. 安装 Claude Code

```bash
npm install -g @anthropic-ai/claude-code
claude --version
```

### 3. 获取配置信息
- **Auth Token**：注册后在 API 令牌页面点击“添加令牌”获得（以 `sk-` 开头）
- **API 地址**：`https://code.wenwen-ai.com`

### 4. 运行 Claude Code

```bash
cd your-project-folder
export ANTHROPIC_AUTH_TOKEN=sk-...
export ANTHROPIC_BASE_URL=https://code.wenwen-ai.com
claude
```

#### 初始化设置
1. 选择你喜欢的主题 + Enter
2. 确认安全须知 + Enter
3. 使用默认 Terminal 配置 + Enter
4. 信任工作目录 + Enter

### 5. 配置环境变量（推荐）
为避免每次重复输入，可将环境变量写入配置文件：

```bash
echo -e '\nexport ANTHROPIC_AUTH_TOKEN=sk-...' >> ~/.bash_profile
echo -e '\nexport ANTHROPIC_BASE_URL=https://code.wenwen-ai.com' >> ~/.bash_profile
echo -e '\nexport ANTHROPIC_AUTH_TOKEN=sk-...' >> ~/.bashrc
echo -e '\nexport ANTHROPIC_BASE_URL=https://code.wenwen-ai.com' >> ~/.bashrc
echo -e '\nexport ANTHROPIC_AUTH_TOKEN=sk-...' >> ~/.zshrc
echo -e '\nexport ANTHROPIC_BASE_URL=https://code.wenwen-ai.com' >> ~/.zshrc
```

重启终端后，直接使用：
```bash
cd your-project-folder
claude
```

---

## 常见问题 FAQ

- **Q: Invalid API Key · Please run /login 怎么解决？**
  - A: 这表明 Claude Code 没有检测到环境变量，请检查 `ANTHROPIC_AUTH_TOKEN` 和 `ANTHROPIC_BASE_URL` 是否配置正确。

- **Q: 显示 offline 是什么原因？**
  - A: Claude Code 会通过检查是否能连接到 Google 来判断网络状态。显示 offline 不影响正常使用。

- **Q: 为什么浏览网页的 Fetch 会失败？**
  - A: 需要保持国际互联网连接并进行全局代理，才能访问 Claude 的网页检测服务。

- **Q: 请求总是显示 fetch failed 怎么办？**
  - A: 可能是网络环境导致的，可以尝试使用备用 API 端点：
    ```bash
    export ANTHROPIC_BASE_URL=https://code.wenwen-ai.com
    ```

---

## 重要提醒
- 本站直接接入官方 Claude Code 转发
- 如遇 API 报错，可以退出重试几次
- 登录错误时可尝试清除本站 Cookie

---

## Netlify 部署说明

1. 在 [Netlify](https://www.netlify.com/) 上注册账号
2. 点击 "New site from Git"
3. 选择你的代码仓库
4. 配置部署设置：
   - Build command: `echo 'No build command needed'`
   - Publish directory: `.`
5. 点击 "Deploy site"

### 自定义域名设置

1. 在 Netlify 控制面板中，进入 "Domain settings"
2. 点击 "Add custom domain"
3. 输入你的域名
4. 按照提示配置 DNS 记录

---

## 本地开发

直接在浏览器中打开 `index.html` 文件即可预览网站。

## 文件结构

- `index.html` - 主页面
- `netlify.toml` - Netlify 配置文件 