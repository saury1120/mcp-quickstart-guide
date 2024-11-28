# MCP 工具列表

本文档提供了 MCP (Model Context Protocol) 所有可用工具的详细说明，按功能分类整理。

## 目录
- [文件系统工具](#文件系统工具)
- [GitHub 工具](#github-工具)
- [数据库工具](#数据库工具)
- [知识图谱工具](#知识图谱工具)
- [网页自动化工具](#网页自动化工具)
- [实用工具](#实用工具)

## 文件系统工具

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `read_file` | 读取单个文件的完整内容 | 查看文件内容，支持多种编码格式 |
| `write_file` | 创建或覆盖文件 | 保存数据或更新文件内容 |
| `list_directory` | 列出指定路径下的文件和目录 | 查看目录结构，带[FILE]/[DIR]标记 |
| `search_files` | 递归搜索匹配文件 | 模糊查找文件 |
| `move_file` | 移动或重命名文件和目录 | 文件重组织、重命名 |
| `create_directory` | 创建目录，支持嵌套 | 建立项目结构 |
| `get_file_info` | 获取文件元数据 | 查看文件属性信息 |
| `read_multiple_files` | 同时读取多个文件 | 批量文件分析比较 |
| `list_allowed_directories` | 列出可访问目录 | 确认操作权限范围 |

## GitHub 工具

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `create_repository` | 创建新仓库 | 开始新项目 |
| `fork_repository` | 复制他人仓库 | 基于现有项目开发 |
| `create_pull_request` | 创建PR | 提交代码合并请求 |
| `create_issue` | 创建Issue | 提交问题或建议 |
| `push_files` | 批量推送文件 | 多文件代码提交 |
| `create_branch` | 创建新分支 | 特性开发或问题修复 |
| `get_file_contents` | 获取仓库文件内容 | 查看远程文件 |
| `search_repositories` | 搜索仓库 | 查找相关项目 |
| `create_or_update_file` | 更新单个文件 | 修改特定文件 |

## 数据库工具

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `read-query` | 执行SELECT查询 | 数据查询 |
| `write-query` | 执行INSERT/UPDATE/DELETE | 数据修改 |
| `create-table` | 创建数据表 | 建立数据结构 |
| `list-tables` | 列出所有表 | 查看数据库结构 |
| `describe-table` | 获取表结构 | 了解字段设计 |

## 知识图谱工具

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `create_entities` | 创建多个实体 | 建立知识节点 |
| `create_relations` | 创建实体关系 | 建立知识连接 |
| `read_graph` | 读取整个图谱 | 查看知识网络 |
| `search_nodes` | 搜索节点 | 查找知识点 |
| `delete_entities` | 删除实体及关系 | 清理旧知识点 |
| `delete_observations` | 删除观察数据 | 更新知识属性 |
| `add_observations` | 添加观察数据 | 补充知识信息 |

## 网页自动化工具

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `puppeteer_navigate` | 导航到URL | 访问网页 |
| `puppeteer_click` | 点击页面元素 | 模拟用户点击 |
| `puppeteer_fill` | 填写输入字段 | 自动填表 |
| `puppeteer_screenshot` | 页面截图 | 保存页面状态 |
| `puppeteer_evaluate` | 执行JavaScript | 操作页面内容 |

## 实用工具

| 工具名称 | 功能说明 | 使用场景 |
|---------|---------|---------|
| `add` | 加法运算 | 数值计算 |
| `echo` | 返回输入内容 | 测试和调试 |
| `longRunningOperation` | 长时间运行操作 | 处理耗时任务 |
| `sampleLLM` | LLM采样 | 语言模型应用 |
| `fetch` | 获取URL内容转Markdown | 网络内容抓取 |

## 使用示例

### 文件操作示例

```python
# 读取文件
content = await read_file("example.txt")

# 写入文件
await write_file("output.txt", "Hello World")

# 搜索文件
files = await search_files("/path/to/dir", "*.py")
```

### GitHub 操作示例

```python
# 创建仓库
repo = await create_repository("my-new-project")

# 提交PR
pr = await create_pull_request(
    title="Add new feature",
    head="feature-branch",
    base="main"
)
```

### 数据库操作示例

```python
# 查询数据
results = await read_query("SELECT * FROM users")

# 创建表
await create_table("""
    CREATE TABLE products (
        id INT PRIMARY KEY,
        name TEXT,
        price DECIMAL
    )
""")
```

## 注意事项

1. 所有工具都支持异步操作，使用时需要使用 `await`
2. 部分工具可能需要特定权限
3. 建议参考官方文档了解每个工具的详细参数
4. 使用前请确保相关依赖已正确安装

## 更多资源

- [官方文档](https://modelcontextprotocol.io/docs)
- [API参考](https://modelcontextprotocol.io/api)
- [示例代码库](https://github.com/anthropics/mcp-examples)
