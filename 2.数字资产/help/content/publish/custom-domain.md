---
title: 自定义域名
date: 2026-02-11
tags:
  - 发布
  - 自定义
  - 域名
---

自定义域名让你使用自己的域名（如 `yourdomain.com`）发布内容，打造专业的个人品牌。

## 🌐 什么是自定义域名？

自定义域名使用你购买的域名：

- **子域名**: `blog.yourdomain.com`
- **根域名**: `yourdomain.com`（Pro/企业账号）

> [!example] 示例
> - `zhangsan.com`
> - `example.com`


## ✨ 优势

### 品牌价值

- 🎯 **专业形象** - 更可信
- 🔗 **品牌一致** - 统一域名
- 📈 **SEO 友好** - 权重累积
- 💼 **商业价值** - 可变现

### 完全掌控

- ✅ 你拥有域名
- ✅ 随时可迁移
- ✅ 无平台限制
- ✅ 长期投资

## 🚀 配置步骤

### 前提条件

- ✅ 已购买域名
- ✅ 有 DNS 管理权限
- ✅ Friday Pro 或以上套餐

### 步骤 1：准备域名

**购买域名**：
- 国内：阿里云、腾讯云
- 国外：GoDaddy、Namecheap

> [!tip] 域名选择
> 
> **好的域名**：
> - `notes.zhangsan.com`
> - `tech-blog.com`
> - `design.studio`
> 
> **避免**：
> - 过长的域名
> - 难以拼写
> - 容易混淆

### 步骤 2：DNS 配置

#### A 记录

如果使用根域名（如 `yourdomain.com`）：

```
类型: A
主机记录: @
记录值: 103.207.68.156 (Friday 提供)
TTL: 600
```

> [!info] DNS 提供商
> 
> **支持的 DNS**：
> - ✅ 腾讯云 DNSPod（推荐）
> - ✅ 阿里云 DNS
> - ✅ Cloudflare
> - ✅ 其他主流 DNS

### 步骤 3：Friday 配置

在 Friday 设置中：

1. 进入 **发布 → 域名设置**
2. 选择"自定义域名"
3. 输入域名（如 `yourdomain.com`）
4. 点击"验证域名"
5. 等待 DNS 生效（通常 1~3 分钟）
6. 点击添加域名，成功后，Friday 会自去申请证书
7. 点击 HTTPS 按钮，查看证书是否准备好（通常 1～3分钟）

> [!success] 免费 SSL
> 
> Friday 使用 Let's Encrypt 免费 SSL 证书：
> - ✅ 自动申请
> - ✅ 自动续期
> - ✅ 无需额外费用

### 多站点支持

Pro 用户可以配置[[site-path|多个路径]]：

| 域名                  | 用途   |
| ------------------- | ---- |
| `example.com/blog`  | 博客   |
| `example.com/docs`  | 文档   |
| `example.com/about` | 个人介绍 |
