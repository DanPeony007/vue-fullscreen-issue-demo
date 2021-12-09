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

![image](https://user-images.githubusercontent.com/41480235/145368865-2c73113d-6f68-48d2-a3cf-e7f197d810ae.png)

### 2、teleport 设置为 false 时，下拉框，popover、drawer等打不开

![image](https://user-images.githubusercontent.com/41480235/145368962-fdd0b9fd-4eb2-4690-abc7-9491388ba25c.png)

### 3、teleport 设置为 true 时，左侧菜单栏遮挡，tinymce 内容丢失

![image](https://user-images.githubusercontent.com/41480235/145369037-044802e1-887c-455f-9fa5-335d264a247f.png)

