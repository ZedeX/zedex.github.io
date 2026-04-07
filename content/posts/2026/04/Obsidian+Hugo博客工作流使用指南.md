---
author: zx
categories:
  - t-tech
date: 2026-04-07T00:06:16+08:00
title: Obsidian + Hugo 博客工作流使用指南
---
终于开始要把WordPress迁移到Hugo的工作完成的差不多了，感谢AI，也启用了Obsidian，通过md文档链接所有。AI帮我写了一个指南。

---

## 一、Obsidian 模板配置步骤

### 1. 启用核心插件"模板"

1. 打开 Obsidian
2. 进入 `设置` → `核心插件`
3. 找到并启用 `模板` (Templates) 插件

### 2. 配置模板插件

1. 进入 `设置` → `模板` (Templates)
2. **模板文件夹位置**：选择 `.obsidian/templates`
3. **日期格式**：设置为 `YYYY-MM-DD`
4. **时间格式**：设置为 `HH:mm:ss`

---

## 二、可用模板

### 1. 新博客文章 - 用于发布到 Hugo

**使用场景**：当你写好一篇文章，准备发布到博客时使用。

**位置**：放在 `content/posts/YYYY/MM/` 目录下

**使用方法**：
1. 在 `content/posts/` 下按年月创建文件夹（如 `2026/04/`）
2. 右键文件夹 → `新建笔记`
3. 按 `Ctrl+P` (或 `Cmd+P` on Mac) 打开命令面板
4. 输入 `模板: 插入模板` (或 `Templates: Insert Template`)
5. 选择 `新博客文章`
6. 填写 `title`（文章标题）
7. 根据需要修改 `category` 分类

**Front Matter 说明**：
```yaml
---
author: zx              # 作者（固定）
categories:               # 分类标签
  - t:-tech            # 技术类文章
  - h:-health          # 健康类
  - x:-x               # 其他
date: "2026-04-06T23:00:00+08:00"  # 发布时间
title: "文章标题"       # 文章标题
---
```

### 2. 草稿笔记 - 用于日常记录

**使用场景**：灵感、草稿、待整理的笔记。

**位置**：放在 `content/_drafts/` 目录下

**使用方法**：
1. 在 `content/_drafts/` 文件夹中新建笔记
2. 使用 `草稿笔记` 模板
3. 随便写，不会被 Hugo 发布

### 3. 新页面 - 用于固定页面

**使用场景**：关于我、本站简介等固定页面。

**位置**：放在 `content/pages/` 目录下

---

## 三、完整工作流

### 写新文章的流程：

```
1. 在 _drafts/ 中创建草稿笔记
   ↓
2. 在 Obsidian 中写作、修改
   ↓
3. 文章完成后，复制到 posts/YYYY/MM/
   ↓
4. 使用「新博客文章」模板添加 front matter
   ↓
5. git commit + push
   ↓
6. GitHub Actions 自动部署 ✨
```

### 图片插入：

**保持原有方式**：使用 `/wp-content/uploads/YYYY/MM/文件名.jpg`

```markdown
![图片说明](/wp-content/uploads/2026/04/photo.jpg)
```

---

## 四、分类标签参考

| 标签 | 说明 |
|------|------|
| `t:-tech` | 技术相关 |
| `h:-health` | 健康/健身 |
| `x:-x` | 其他/杂项 |
| `l:-life` | 生活/日常 |
| `f:-finance` | 财务/投资 |

---

## 五、快速开始示例

### 示例：发布一篇新文章

1. **创建草稿**（可选）：
   - 在 `_drafts/` 新建 `我的新文章.md`
   - 用「草稿笔记」模板，开始写作

2. **准备发布**：
   - 在 `posts/2026/04/` 新建文章
   - 按 `Ctrl+P` → 输入「模板」→ 选「新博客文章」
   - 填写 `title`，把草稿内容粘贴过来

3. **提交发布**：
   ```bash
   git add .
   git commit -m "feat: 添加新文章"
   git push
   ```

4. **等待部署**：GitHub Actions 会自动构建并部署！

---

## 六、注意事项

⚠️ **重要**：
- 只有 `posts/` 和 `pages/` 下的文章会被 Hugo 构建
- `_drafts/` 下的内容不会发布
- 确保 front matter 格式正确（YAML，用 `---` 包裹）
- 图片路径保持 `/wp-content/uploads/...` 格式

