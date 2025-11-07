# 🍳 最终项目前端框架说明（Final Project Skeleton）

本仓库作为我们最终课程项目（Final Project）的前端基础框架。当前版本以我在 MP2 宝可梦搜索引擎项目为蓝本修改而来，用于提供前端结构、组件模板、数据展示逻辑等基础代码。后续我们将基于此项目扩展出完整的后端 API（Node.js + Express）和 MongoDB 数据库支持。

本项目的目标是构建一个数据库驱动的全栈 Web 应用，包括前端、后端和数据库三部分。前端使用 React + TypeScript 构建；后端使用 Node.js + Express 实现 RESTful API；数据库使用 MongoDB Atlas 存储菜谱数据。系统最终还将实现用户注册、登录与权限验证等功能。当前仓库仅包含前端部分，便于组员先行进行页面结构设计、UI/UX 开发与数据展示。

---

## 🚀 启动方式

1. 克隆仓库  
   `git clone <本仓库地址>`

2. 进入项目文件夹  
   `cd Final`

3. 安装依赖  
   `npm install`

4. 启动前端项目  
   `npm start`

运行后访问 [http://localhost:3000](http://localhost:3000) 即可查看页面。  
目前数据来自本地 `recipes_cleaned.json` 文件，后续会替换为数据库中的动态数据。

---

## 📁 文件与目录结构

```
Final/
├── public/                  # 静态资源目录
│   ├── Food Images/         # 食物图片素材
│   └── index.html
├── src/                     # 前端主要代码（React + TypeScript）
│   ├── components/          # 可复用组件
│   ├── pages/               # 页面文件
│   └── index.tsx            # 前端入口
├── recipes_cleaned.json     # 清理后的菜谱数据文件
├── package.json             # npm 配置文件
└── README.md                # 项目说明文档
```

---

## 🥗 数据说明

本项目的数据文件为 `recipes_cleaned.json`，这是清理后的菜谱数据，结构规范、字段统一。主要字段包括：  
- **Title**：菜谱标题  
- **Ingredients**：原始配料（字符串数组）  
- **Instructions**：制作步骤  
- **Extracted_Ingredients**：提取的标准化食材名称  
- **Image_Name**：对应图片文件名  

当后端与数据库搭建完成后，此文件将被导入 MongoDB Atlas 数据库中，并通过 API 提供给前端调用。  

所有食物图片放置于 `/public/Food Images/` 文件夹中。这些图片将在前端的图库（Gallery）或详情页中展示，命名与 `recipes_cleaned.json` 中的 `Image_Name` 一一对应。请务必保持命名一致，否则页面加载会出错。

---

## 💻 前端运行与开发说明

前端基于 Create React App + TypeScript 构建，支持组件化开发与响应式布局。运行步骤如下：  

`npm install`  
`npm start`  

运行后将在本地开启开发服务器。所有静态图片文件需放在 `/public/Food Images/` 路径下，前端代码（组件、页面、样式）位于 `/src`。若出现端口冲突，可在项目根目录创建 `.env` 文件并指定端口号：  

`PORT=3001`  

---

## ⚙️ 后端与数据库开发计划

后端将使用 Node.js + Express 实现，并连接 MongoDB Atlas。后端功能包括：  
- 用户注册与登录（JWT 认证）  
- 菜谱数据的增删改查（CRUD）  
- 用户收藏或自定义菜谱功能  
- API 路由设计与数据过滤  
- 安全处理（输入验证、CORS、密码加密）  

API 路由初步设计如下：  
| 模块 | 功能 |  
|------|------|  
| `/api/recipes` | 查询 / 新增 / 修改 / 删除菜谱 |  
| `/api/auth` | 用户注册 / 登录 / JWT 鉴权 |  
| `/api/users` | 用户资料管理 |  
| `/api/favorites` | 用户收藏菜谱 |  

---



**项目维护者：** Pete Chen (`peteoyhh`)  
**最后更新日期：** 2025 年 11 月
