# Model Context Protocol (MCP) 快速入门指南

Model Context Protocol (MCP) 是由 Anthropic 开源的一个新标准协议，旨在解决 AI 助手与数据系统之间的连接问题。本仓库提供了 MCP 的详细介绍、工具清单以及快速启动指南。

## 目录

- [简介](#简介)
- [核心特性](#核心特性)
- [快速开始](#快速开始)
- [工具列表](#工具列表)
- [示例](#示例)
- [贡献指南](#贡献指南)

## 简介

MCP 通过提供统一的开放标准，替代了以往分散的集成方式，使 AI 系统能够更便捷地访问各种数据源。它的主要目标是帮助前沿模型产生更好、更相关的响应。

### 为什么选择 MCP？

- **统一标准**: 提供通用协议，避免重复开发
- **双向连接**: 支持 AI 系统和数据源之间的安全双向通信
- **简单集成**: 易于实现和扩展
- **开源生态**: 活跃的开发者社区和丰富的工具支持

### 架构概览

![MCP Overview](./images/mcp-overview.svg)

## 核心特性

1. **标准化连接**
   - 统一的数据访问接口
   - 标准化的通信协议
   - 可扩展的架构设计

2. **安全性**
   - 安全的双向连接
   - 访问控制机制
   - 数据隔离保护

3. **灵活性**
   - 支持多种数据源
   - 可自定义扩展
   - 跨平台兼容

## 快速开始

### 前置条件

- Python 3.8+ 或 Node.js 14+
- Claude Desktop App（可选）

### 基本用法

1. **安装**

```bash
# Python
pip install mcp-python

# Node.js
npm install @anthropic-ai/mcp-node
```

2. **创建服务器**

```python
from mcp import MCPServer

# 创建 MCP 服务器
server = MCPServer()

# 注册资源
@server.resource
def get_data():
    return {"message": "Hello from MCP!"}

# 启动服务器
server.start()
```

## 工具列表

MCP 提供了丰富的工具集，详细信息请查看 [tools.md](./docs/tools.md)

## 常见用例

### 1. 文件系统集成

```python
@server.tool
def read_file(path: str):
    with open(path, 'r') as f:
        return f.read()
```

### 2. 数据库连接

```python
@server.tool
def query_database(sql: str):
    # 实现数据库查询逻辑
    pass
```

## 贡献

我们欢迎任何形式的贡献！

## 许可证

本项目采用 MIT 许可证

## 相关资源

- [官方文档](https://modelcontextprotocol.io)
- [API 参考](https://modelcontextprotocol.io/api)
- [示例仓库](https://github.com/anthropics/mcp-examples)