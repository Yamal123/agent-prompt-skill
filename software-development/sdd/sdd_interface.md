---
name: sdd_interface
display_name: SDD 接口设计
version: V1.0
description: 生成软件设计文档的接口定义章节；当用户要求"API 设计、接口规范、RESTful"时触发
compatibility: All
tags: [sdd, api, 接口]
---

# Skill：SDD 接口设计

## 触发词
- API 设计
- 接口规范
- RESTful
- 接口定义

## 适用场景
前后端接口对接、微服务 API 设计、接口文档编写

## 禁忌场景
数据库设计、业务逻辑实现、前端页面开发

## 执行步骤
1. 识别对外暴露的接口端点
2. 定义请求/响应数据结构
3. 指定 HTTP 方法与状态码
4. 添加认证授权要求
5. 输出标准化接口文档

## 输出模板
```markdown
## 3. 接口设计

### 3.1 接口规范
- 协议：HTTPS
- 版本：v1
- 路径前缀：/api/v1

### 3.2 接口列表

#### 3.2.1 用户登录
- **路径**: `POST /api/v1/auth/login`
- **描述**: 用户登录获取 Token

**请求体**:
```json
{
  "username": "string // 用户名",
  "password": "string // 密码"
}
```

**成功响应** (200):
```json
{
  "code": 0,
  "message": "success",
  "data": {
    "token": "string",
    "user": {}
  }
}
```

**失败响应** (401):
```json
{
  "code": 401,
  "message": "用户名或密码错误"
}
```
```

## 校验标准
- 接口路径、方法、描述完整
- 请求/响应结构包含字段类型与注释
- 状态码覆盖成功与失败场景
- 符合 RESTful 规范

## 异常处理
- 接口需求不明确时返回「请提供接口功能、参数、返回值要求」
- 复杂业务场景建议先进行需求梳理