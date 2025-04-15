# Mock.js 详解

## 1. 基本定义

`Mock.js` 是一个用于**前端开发**的模拟数据生成库，主要解决以下问题：

- 后端 API 未完成时的**前端独立开发**
- 单元测试的**数据模拟需求**
- 快速生成**结构化随机数据**

## 2. 核心功能

### 数据生成

```javascript
// 生成包含随机数据的对象
Mock.mock({
  "list|5": [
    {
      "id|+1": 1,
      name: "@cname", // 随机中文名
      "age|18-60": 1, // 18-60随机数
      email: "@email", // 随机邮箱
    },
  ],
});
```

### 请求拦截

```javascript
// 拦截AJAX请求并返回模拟数据
Mock.mock("/api/users", "get", {
  "data|10": [{ id: "@id", name: "@cname" }],
});
```

## 3. 核心语法

| 语法           | 示例                 | 输出示例   |
| -------------- | -------------------- | ---------- | ------------------ |
| **基本占位符** | `'name': '@first'`   | "John"     |
| **数量范围**   | `'list               | 1-10': []` | 生成 1-10 个数组项 |
| **递增 ID**    | `'id                 | +1': 1`    | 1,2,3...           |
| **随机图片**   | `'avatar': '@image'` | 图片 URL   |

## 4. 工程化应用

### 目录结构建议

```
mock/
├── index.js            # 入口文件
├── user.mock.js        # 用户相关Mock
└── product.mock.js     # 商品相关Mock
```

### 生产环境禁用

```javascript
// vite.config.js
export default defineConfig({
  define: {
    __USE_MOCK__: process.env.NODE_ENV === "development",
  },
});
```

## 5. 同类工具对比

| 特性           | Mock.js    | JSON Server | MSW        |
| -------------- | ---------- | ----------- | ---------- |
| **数据随机性** | ⭐⭐⭐⭐⭐ | ⭐⭐        | ⭐⭐⭐     |
| **REST 支持**  | ⭐⭐       | ⭐⭐⭐⭐⭐  | ⭐⭐⭐⭐   |
| **请求拦截**   | ⭐⭐⭐⭐   | ⭐          | ⭐⭐⭐⭐⭐ |

## 6. 最佳实践

- 配合`axios`拦截器实现开发/生产环境切换
- 使用`@mockjs/better-mock`增强版获得 TS 支持
- 对敏感字段做脱敏处理（如手机号生成规则）

> 官方文档：[Mock.js 官网](http://mockjs.com/)
