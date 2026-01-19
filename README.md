# apps
附加的参赛用的小应用集合

## 项目介绍

本仓库包含了多个用于参赛的小应用，每个应用都是独立的项目，具有完整的功能和代码结构。这些应用主要基于现代Web技术栈开发，旨在展示各种功能和解决方案。

## 应用列表

### app-8xw8mc7ujcht - 智能日报管理系统

**应用链接**: https://www.miaoda.cn/projects/app-8xw8mc7ujcht

**项目概述**:
一个基于React和Supabase的智能日报管理系统，帮助团队和个人高效记录和分析日常工作情况。系统集成了Git提交记录分析、AI翻译、工作趋势分析等功能，提供直观的数据可视化界面。

**核心功能模块**:

#### 1. 仪表盘 (HomePage)
- 工作统计概览：总日报数、总提交数、活跃天数等
- 最近生成的日报列表
- 活跃的工作阻塞项展示
- 数据可视化卡片展示

#### 2. 日报管理 (DailyReportPage)
- 手动/自动生成日报
- Git提交记录导入与分析
- 工作内容分类记录（已完成工作、重要性说明、阻塞项）
- AI翻译功能（支持多种翻译风格）
- 语音笔记功能
- 实时保存与更新

#### 3. Git配置管理
- Git仓库连接与配置
- 自动同步提交记录
- 分支管理

#### 4. 历史记录
- 查看历史日报记录
- 按日期筛选和搜索
- 导出功能

#### 5. 趋势分析
- 工作活跃度分析
- 提交记录统计
- 时间分布分析
- 趋势图表展示

#### 6. 系统设置
- 用户配置管理
- 通知设置
- 翻译风格选择
- 自动拉取时间配置

**技术栈详细信息**:

- **前端框架**: React 18
- **构建工具**: Vite 5
- **编程语言**: TypeScript 5.9
- **UI组件库**: Radix UI + Tailwind CSS 3
- **数据库**: Supabase (PostgreSQL)
- **认证**: Supabase Auth
- **状态管理**: React Context API
- **路由**: React Router 7
- **日期处理**: date-fns
- **图表库**: Recharts
- **UI工具库**: lucide-react (图标), sonner (通知), clsx (类名管理)
- **表单处理**: react-hook-form + zod
- **动画**: motion

**核心数据结构**:

- `DailyReport`: 日报记录，包含日期、Git提交、工作内容、阻塞项等
- `GitCommit`: Git提交记录，包含哈希、消息、作者、文件变更等
- `Blocker`: 工作阻塞项，包含严重程度和状态
- `Statistics`: 统计数据，包含日报数、提交数、活跃天数等
- `WorkTrend`: 工作趋势数据，包含提交统计和活跃度评分

## 目录结构

```
├── app-8xw8mc7ujcht/  # 智能日报管理系统
│   ├── public/         # 静态资源目录
│   │   ├── images/     # 图片资源
│   │   │   ├── error/  # 错误页面图片
│   │   │   └── logo/   # 应用图标
│   ├── src/            # 源码目录
│   │   ├── components/ # UI组件
│   │   ├── contexts/   # React上下文
│   │   ├── db/         # 数据库配置与API
│   │   ├── hooks/      # 自定义Hooks
│   │   ├── pages/      # 页面组件
│   │   ├── services/   # 服务层
│   │   ├── types/      # TypeScript类型定义
│   │   ├── utils/      # 工具函数
│   │   ├── App.tsx     # 应用入口组件
│   │   ├── main.tsx    # 应用启动文件
│   │   └── routes.tsx  # 路由配置
│   ├── supabase/       # Supabase配置
│   │   ├── functions/  # Supabase边缘函数
│   │   └── migrations/ # 数据库迁移文件
│   ├── .env            # 环境变量
│   ├── package.json    # 项目依赖
│   ├── tailwind.config.js # Tailwind配置
│   └── vite.config.ts  # Vite配置
└── README.md           # 仓库说明文档
```

## 本地开发指南

### 环境要求

- Node.js ≥ 20
- npm ≥ 10 或 pnpm
- Supabase CLI (可选，用于本地开发)

### 开发步骤

1. **进入应用目录**
   ```bash
   cd app-8xw8mc7ujcht
   ```

2. **安装依赖**
   ```bash
   npm install
   # 或
   pnpm install
   ```

3. **配置环境变量**
   - 复制 `.env.example` 为 `.env`
   - 填写Supabase连接信息和其他必要的环境变量

4. **启动开发服务器**
   ```bash
   npm run dev
   # 或
   pnpm dev
   ```

5. **访问应用**
   - 打开浏览器访问 `http://localhost:5173`

### 后端开发

- 应用使用Supabase作为后端服务
- 数据库迁移文件位于 `supabase/migrations/`
- 边缘函数位于 `supabase/functions/`

## 项目特色

1. **智能自动化**:
   - 自动从Git仓库拉取提交记录
   - AI辅助生成日报内容
   - 智能翻译支持多种风格

2. **数据可视化**:
   - 工作趋势图表分析
   - 活跃度分布展示
   - 直观的统计卡片

3. **用户体验优化**:
   - 响应式设计，支持移动端
   - 实时保存功能
   - 友好的错误提示

4. **安全性**:
   - 基于Supabase的认证系统
   - 权限控制
   - 环境变量管理

## 注意事项

- 应用需要Supabase服务支持，请确保已配置正确的Supabase连接信息
- 部分功能可能需要特定的API密钥（如AI翻译）
- 开发前请仔细阅读各应用目录下的README.md文件

## 许可证

MIT License
