# 站点素材

此目录用于保存你确认可公开使用的素材。当前站点无需图片即可完整显示，不包含虚构头像或 CV。

## CV

放入 `cv.pdf` 后，在 `index.html` 的 CV 区块按注释启用下载链接。仅上传文件不会自动改变页面。文件名区分大小写。

## 个人照片（可选）

建议文件名 `profile.jpg`，约 800 × 1000 像素，压缩到 500 KB 以下。你可以在 `index.html` 的 `hero-copy` 中按需要添加：

```html
<img src="assets/profile.jpg" alt="Portrait of Xingqi Pan" width="160" height="200" style="max-width:100%;height:auto;object-fit:cover">
```

页面目前没有照片占位或失效图片请求。无需照片也可以直接上线。

## 论文和其他附件

可使用清晰的英文文件名，文件链接采用相对路径 `assets/文件名`。仅上传获准公开的文件；论文也可直接链接 DOI，不必上传 PDF。
