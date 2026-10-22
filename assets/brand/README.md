# Brand assets

Official CCNVR marks used by the README, the GitHub repository and the release pages.

| File | Size | Use |
| --- | --- | --- |
| `ccnvr-logo.png` | 208 × 224 | Primary mark, black on transparent — light backgrounds |
| `ccnvr-logo-dark.png` | 208 × 224 | White mark — dark backgrounds and GitHub dark mode |
| `ccnvr-icon-512.png` | 512 × 512 | Repository avatar, app icon, favicon source |
| `social-preview.png` | 1280 × 640 | GitHub **Settings → Social preview** |

`README.md` and `README.zh-CN.md` switch between the light and dark marks automatically:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/brand/ccnvr-logo-dark.png">
  <img src="assets/brand/ccnvr-logo.png" alt="CCNVR" width="140">
</picture>
```

Guidelines:

- Keep clear space around the mark of at least half its height.
- Do not stretch, rotate, recolor or add effects to the mark.
- Do not place the black mark on a dark background — use `ccnvr-logo-dark.png` there.
- Minimum display width: 96 px for the mark, 32 px for the square icon.

---

# 品牌素材

CCNVR 官方标识，供 README、GitHub 仓库和发布页使用。

| 文件 | 尺寸 | 用途 |
| --- | --- | --- |
| `ccnvr-logo.png` | 208 × 224 | 主标识，黑色透明底，用于浅色背景 |
| `ccnvr-logo-dark.png` | 208 × 224 | 白色标识，用于深色背景和 GitHub 深色模式 |
| `ccnvr-icon-512.png` | 512 × 512 | 仓库头像、应用图标、favicon 源图 |
| `social-preview.png` | 1280 × 640 | GitHub「Settings → Social preview」 |

使用规范：

- 标识四周留白不少于其高度的一半。
- 不要拉伸、旋转、改色或添加特效。
- 黑色标识不要放在深色背景上，请改用 `ccnvr-logo-dark.png`。
- 最小显示宽度：主标识 96 px，方形图标 32 px。
