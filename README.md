# 数据库访问服务 DB Mcp

MCP Database Server 是一个为AI助手和基于LLM的工具提供安全数据库访问的服务，支持SQLite、PostgreSQL、MySQL和MariaDB，具有查询验证、审计日志和安全控制功能。
MCP Database Server is a service that provides secure database access for AI assistants and LLM-based tools, supporting SQLite, PostgreSQL, MySQL and MariaDB, and featuring query verification, audit logs and security control functions.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| db_tables | List all tables in the database, optionally filtered by schema. Returns qualified table names. |
| db_describe_table | Get column information for a specific table including column names, data types, and nullability. |
| db_execute | Execute a SQL statement. Supports SELECT (read), INSERT/UPDATE/DELETE (write if enabled), and DDL (if enabled). Use named parameters with :param syntax. |
| db_explain | Get query execution plan and performance information using EXPLAIN. Helps analyze query performance and optimization opportunities. |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659322883](https://mcp.xiaobenyang.com/inspector/1777316659322883)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659322883](https://mcp.xiaobenyang.com/inspector/1777316659322883)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "数据库访问服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659322883/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "数据库访问服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659322883/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "数据库访问服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659322883",
          },
          "transport": "stdio"
        }
      }
}

```
