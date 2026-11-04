# mewcode

一个终端 AI 编程助手（对标 Claude Code），完整实现 Agent 工程机制。

> ⚠️ **源码来源说明**：本项目源码来自「小林 coding」（xiaolincoding.com）的教程项目，本人仅用于学习 Agent 开发、研究落地级 Agent 架构，**非本人原创**。学习笔记与复刻版本见我的其他仓库。

## 功能

- **Agent 核心循环**：事件驱动 + 流式输出（StreamText / ToolUseEvent / ToolResultEvent / UsageEvent）
- **30+ 工具**：bash / edit_file / grep / glob / read_file / write_file / task / team / mcp_call…
- **权限系统 + 系统沙箱**：危险命令检测 + 模式（default/plan/bypass）+ bwrap（Linux）/ seatbelt（macOS）
- **MCP 协议**：stdio / Streamable HTTP / SSE 三种传输
- **多 Agent 协作**：teams（coordinator / mailbox / protocol / spawn，支持 inprocess/tmux/iTerm2）
- **记忆系统**：auto_memory / consolidation / recall / instructions
- **上下文压缩**：含 tool_calls 与结果配对的保护（避免拆断协议）
- **16+ 内置命令**：clear / compact / plan / review / rewind / sandbox / session / skill / trace…
- **界面**：textual TUI + Web 模式（WebSocket）

## 技术栈

Python 3.11+ · textual · anthropic / openai（双协议）· pydantic · MCP · asyncio · websockets

## 运行

```bash
uv sync
cp .mewcode/config.yaml.example .mewcode/config.yaml   # 填 API key
uv run mewcode
```
