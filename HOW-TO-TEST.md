# 本地测试运行指南

## 项目结构

纯静态前端项目（HTML + CSS + JS），无需构建工具。

```
FilMBTI/
├── index.html
├── script.js
├── style.css
└── images/
```

---

## 方法一：VS Code Live Server（推荐）

1. 在 VS Code 中打开 `FilMBTI/` 文件夹
2. 安装扩展：**Live Server**（Ritwick Dey）
3. 右键 `index.html` → **Open with Live Server**
4. 浏览器自动打开 `http://127.0.0.1:5500`
5. 修改文件后页面自动刷新

---

## 方法二：Python 本地服务器

在终端进入项目目录，执行：

```bash
cd "C:\Users\Kaight\Desktop\2026\Filmbti\FilMBTI"

# Python 3
python -m http.server 8080
```

然后浏览器访问：`http://localhost:8080`

---

## 方法三：Node.js serve

```bash
# 安装（只需一次）
npm install -g serve

# 运行
cd "C:\Users\Kaight\Desktop\2026\Filmbti\FilMBTI"
serve .
```

访问终端提示的地址，通常是 `http://localhost:3000`

---

## 注意：不能直接双击打开

直接用浏览器打开 `index.html`（`file://` 协议）会导致：
- 图片加载失败（跨域限制）
- Google 表单提交被拦截
- 部分功能异常

**必须通过本地服务器访问（`http://localhost:...`）。**

---

## 验证 Google 表单提交

1. 完成一次测试，到达结果页
2. 打开浏览器开发者工具（F12）→ Network 标签
3. 筛选关键词 `formResponse`
4. 应看到一条 POST 请求，状态显示 `(opaque)`（no-cors 正常现象）
5. 去 Google 表单后台 → 查看回复，确认数据已收到

---

## 验证新角色（赫敏·格兰杰）

1. 选择性别：女
2. 答题时尽量偏向「规则、准备、信念」方向（I/S/T/J 倾向）
3. 到达分支题时选择 **B（信念驱动）**
4. 结果页应显示赫敏·格兰杰

选 A（恐惧驱动）则显示莎拉·康纳。
