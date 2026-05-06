# 供应商核销系统

> 一个完整的供应商核销解决方案，包含后台管理系统和H5移动端

## 🏗️ 项目结构

```
vendor-verification-system/
├── admin/          # 后台管理系统（Web）
├── h5/             # H5移动端核销端
├── package.json    # 根 package.json（Monorepo）
├── pnpm-workspace.yaml  # pnpm workspace 配置
├── tsconfig.json   # TypeScript 全局配置
└── README.md       # 本文件
```

## 🛠️ 技术栈

- **Vue 3** - 渐进式 JavaScript 框架
- **TypeScript** - JavaScript 的超集
- **Vite** - 下一代前端构建工具
- **Pinia** - Vue 3 状态管理
- **Vue Router 4** - 官方路由管理
- **Element Plus** / **Ant Design Vue** - UI 框架（待选）
- **Axios** - HTTP 请求库
- **Vant** - 移动端 UI 框架（H5）

## 📦 项目特性

- ✅ Monorepo 架构，统一管理多个应用
- ✅ Vite 高速开发和构建
- ✅ TypeScript 类型安全
- ✅ 后台管理系统（ADMIN）
  - 多页面应用
  - 权限管理
  - 完整的数据管理功能
- ✅ H5 移动端（H5）
  - 响应式设计
  - 移动端友好

## 🚀 快速开始

### 前置要求

- Node.js >= 16
- pnpm >= 8

### 安装依赖

```bash
# 使用 pnpm 安装所有工作区依赖
pnpm install
```

### 开发模式

```bash
# 同时启动所有应用
pnpm dev

# 仅启动后台管理系统
pnpm dev:admin

# 仅启动 H5 移动端
pnpm dev:h5
```

### 构建生产版本

```bash
# 构建所有应用
pnpm build

# 仅构建后台管理系统
pnpm build:admin

# 仅构建 H5 移动端
pnpm build:h5
```

### 预览生产构建

```bash
# 预览所有应用
pnpm preview

# 仅预览后台管理系统
pnpm preview:admin

# 仅预览 H5 移动端
pnpm preview:h5
```

## 📂 工作区配置

本项目使用 `pnpm workspaces` 进行 Monorepo 管理：

### Admin (后台管理系统)
- **路径**: `./admin`
- **开发端口**: `5173`
- **功能**: 订单管理、售后管理、账号管理等

### H5 (移动端核销端)
- **路径**: `./h5`
- **开发端口**: `5174`
- **功能**: 扫码核销、售后申请等

## 🔧 配置文件说明

### pnpm-workspace.yaml
定义了 Monorepo 工作区，包括 `admin` 和 `h5` 两个包

### tsconfig.json
- **target**: ES2020
- **module**: ESNext
- **strict**: true（严格模式）
- **jsx**: react-jsx

### 路径别名
```json
{
  "paths": {
    "@/*": ["./*"]
  }
}
```

在代码中使用 `@/` 前缀来引入相对路径

## 📝 环境变量

在各个应用根目录创建 `.env.local` 文件：

```env
# Admin
VITE_API_BASE_URL=http://localhost:3000
VITE_APP_NAME=供应商核销端

# H5
VITE_API_BASE_URL=http://localhost:3000
VITE_APP_NAME=核销端
```

详见各应用目录的 `.env.example` 文件

## 📚 项目文档

- [产品需求文档 (PRD)](./PRD.md)
- [Admin 项目文档](./admin/README.md)
- [H5 项目文档](./h5/README.md)

## 🤝 贡献指南

1. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
2. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
3. 推送到分支 (`git push origin feature/AmazingFeature`)
4. 开启 Pull Request

## 📄 License

MIT License

## 🎯 开发规范

### 文件命名
- 组件文件：PascalCase (如 `UserProfile.vue`)
- 普通文件：camelCase (如 `userService.ts`)
- 文件夹：kebab-case (如 `user-profile/`)

### 代码风格
- 使用 TypeScript 进行类型检查
- 遵循 ESLint 规则
- 提交前运行 `pnpm lint`

### Git 提交规范
```
feat: 新功能
fix: 修复bug
docs: 文档更新
style: 代码风格调整
refactor: 代码重构
perf: 性能优化
test: 测试相关
```

## 📞 联系方式

如有任何问题，请提交 Issue 或联系开发团队。
