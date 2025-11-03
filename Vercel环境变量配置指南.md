# 🔑 Vercel 环境变量配置指南

## ⚠️ 重要：本地和 Vercel 需要分别配置

### 本地开发（已完成 ✅）
- 文件：`.env.local`
- 位置：`E:\LTNS\.env.local`
- 内容：`OPENAI_API_KEY=你的密钥`

### Vercel 部署（需要配置 ⚠️）
- 位置：Vercel Dashboard
- 方式：Environment Variables
- 必须手动配置！

---

## 📋 Vercel 环境变量配置步骤

### 步骤 1：登录 Vercel

1. 访问：https://vercel.com/dashboard
2. 登录你的账户

### 步骤 2：进入项目设置

1. 找到你的项目（recheers）
2. 点击项目进入详情页
3. 点击 **Settings**（设置）

### 步骤 3：配置环境变量

1. 在左侧菜单点击 **Environment Variables**（环境变量）
2. 点击 **Add New**（添加新变量）按钮

3. 填写信息：
   ```
   Name: OPENAI_API_KEY
   Value: 你的DeepSeek_API密钥
   ```

4. **选择环境**（重要！）：
   - ✅ Production（生产环境）
   - ✅ Preview（预览环境）
   - ✅ Development（开发环境）
   
   建议全部勾选

5. 点击 **Save**（保存）

### 步骤 4：重新部署

配置环境变量后：

**方法 A：自动触发**
- Vercel 会自动检测并重新部署（如果有最近的推送）

**方法 B：手动触发**
1. 进入 **Deployments** 标签
2. 找到最新的部署
3. 点击右侧的 **...**（三个点）
4. 选择 **Redeploy**（重新部署）

---

## 🔍 验证配置

### 检查环境变量：

1. Settings → Environment Variables
2. 确认看到：
   ```
   OPENAI_API_KEY    [已配置]    [所有环境]
   ```

### 检查部署日志：

1. Deployments → 最新的部署 → Build Logs
2. 应该不再看到 "OpenAI API key not configured" 错误
3. 构建应该成功完成

### 测试网站：

1. 访问你的 Vercel 网站 URL
2. 尝试使用 AI 聊天功能
3. 应该能正常工作

---

## ⚠️ 常见问题

### Q1: 配置后还是显示 API key not configured

**检查**：
- [ ] 环境变量名称是否正确：`OPENAI_API_KEY`（全大写）
- [ ] 是否选择了正确的环境（Production/Preview/Development）
- [ ] 是否重新部署了（配置后需要重新部署才生效）

### Q2: 本地可以但 Vercel 不行

**原因**：本地用 `.env.local`，Vercel 需要单独配置

**解决**：在 Vercel Dashboard 中配置环境变量

### Q3: 如何更新密钥

1. Settings → Environment Variables
2. 找到 `OPENAI_API_KEY`
3. 点击编辑（铅笔图标）
4. 更新值
5. 保存
6. 重新部署

---

## 📝 配置摘要

| 配置项 | 本地 | Vercel |
|--------|------|--------|
| **文件/位置** | `.env.local` | Dashboard → Environment Variables |
| **变量名** | `OPENAI_API_KEY` | `OPENAI_API_KEY` |
| **是否需要配置** | ✅ 已配置 | ⚠️ **需要配置** |
| **如何更新** | 编辑文件 | Dashboard 中编辑 |

---

## ✅ 完成配置后

1. ✅ 环境变量已配置
2. ✅ 代码已推送到 GitHub
3. ✅ Vercel 重新部署
4. ✅ 网站应该可以正常工作了！

---

**记住**：Vercel 不会自动读取 `.env.local`，必须手动在 Dashboard 中配置！

