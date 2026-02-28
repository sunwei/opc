---
title: 多站点指南
weight: 5
tags:
  - 发布
  - 多站点
---

## 站点路径

站点路径决定了你的网站在 URL 中的位置。正确配置 SitePath 对网站正常运行至关重要。

---

## 什么是站点路径？

站点路径是网站的 **基础 URL 路径**。

> [!success] 所有发布方式都支持站点路径

示例：
- SitePath `/` → 网站在 `https://example.com/`
- SitePath `/blog` → 网站在 `https://example.com/blog/`
- SitePath `/docs/v2` → 网站在 `https://example.com/docs/v2/`

---

## 为什么站点路径很重要

站点路径影响：

| 方面 | 影响 |
|------|------|
| **页面链接** | 所有内部链接根据 SitePath 生成 |
| **资源路径** | CSS、JS、图片加载路径 |
| **导航** | 菜单、面包屑链接 |
| **SEO** | 搜索引擎索引的 URL 结构 |

> [!danger] SitePath 错误 = 网站崩溃
> 
> 如果 SitePath 配置错误：
> - 页面无法加载
> - 样式丢失（显示为纯文本）
> - 链接返回 404 错误



