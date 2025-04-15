# 1. 创建工程

## 创建 Vue3 工程

```shell
yarn create vue
```

创建工程的时候选择了以下选项：

- pinia : 状态管理
- vue-router : 路由
- eslint : 代码规范
- prettier : 代码格式化
- vitest : 单元测试
- cypress : 端到端测试

## 目录结构

创建出如下目录结构：

```shell
.
├── cypress # 端到端测试
│   ├── e2e
│   │   └── example.cy.js
│   ├── fixtures
│   │   └── example.json
│   ├── jsconfig.json
│   └── support
│       ├── commands.js
│       └── e2e.js
├── cypress.config.js # cypress配置
├── eslint.config.js # eslint配置
├── index.html 
├── jsconfig.json # js配置  
├── package.json
├── public # 静态资源
│   └── favicon.ico
├── README.md
├── src # 源码
│   ├── App.vue
│   ├── assets # 静态资源
│   │   ├── base.css
│   │   ├── logo.svg
│   │   └── main.css
│   ├── components # 组件
│   │   ├── HelloWorld.vue
│   │   ├── icons
│   │   │   ├── IconCommunity.vue
│   │   │   ├── IconDocumentation.vue
│   │   │   ├── IconEcosystem.vue
│   │   │   ├── IconSupport.vue
│   │   │   └── IconTooling.vue
│   │   ├── __tests__
│   │   │   └── HelloWorld.spec.js
│   │   ├── TheWelcome.vue
│   │   └── WelcomeItem.vue
│   ├── main.js
│   ├── router # 路由
│   │   └── index.js
│   ├── stores # 状态管理
│   │   └── counter.js
│   └── views # 视图
│       ├── AboutView.vue
│       └── HomeView.vue
├── vite.config.js # vite配置
└── vitest.config.js # vitest配置
```
