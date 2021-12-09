# vue-fullscreen-issue-demo
复现 vue-fullscreen 使用时，全屏元素含有 iframe 时的问题的 demo

## 开始项目

```bash
# 克隆项目
git clone https://github.com/DanPeony007/vue-fullscreen-issue-demo

# 安装依赖
npm install

# 启动服务
npm run dev
```

浏览器访问 http://localhost:9527

## 问题描述

### 1、未全屏时，正常显示

[图片]![image](https://user-images.githubusercontent.com/41480235/145392277-246da675-ca44-4ba2-b934-76f208c23fa1.png)

### 2、teleport 设置为 false 时，下拉框，popover、drawer等打不开

[图片]![image](https://user-images.githubusercontent.com/41480235/145392299-ddc4c6a9-aaca-4994-b326-81579e47ea81.png)

### 3、teleport 设置为 true 时，tinymce 内容丢失（iframe 中 body 为空）

[图片]![image](https://user-images.githubusercontent.com/41480235/145392317-498333cb-47fd-4d63-8dfe-c050bbc60b6d.png)
