---
name: project-init
description: Use when the user asks to initialize a new project or introduce their shared project standards, layered Java skeleton, common classes, quality tools, or Codex hooks into an existing project. Also applies to 项目初始化、初始化项目、接入通用规范。
---

# 项目初始化

通用规范根目录为本技能文件所在目录的 `../../spec`。首先读取 [scripts/INIT.md](../../spec/scripts/INIT.md)，按其中流程收集信息、执行初始化并验证；文档和脚本为唯一维护来源，不复制一套到技能中。

- **目标目录必须由用户明确指定。** 用户未提供时先询问项目绝对路径；相对路径须说明解析后的绝对路径并请用户确认。禁止默认使用当前目录或自行创建项目位置。
- 复用用户已给出的明确配置及已有项目事实，只询问缺失或冲突的信息：初始化范围、基础包名、技术栈和版本、模块及通用类归属。路径已明确时无需重复确认。
- 使用规范中的 `scripts/init-project.sh`，参数来自已确定的信息；遇到已有文件冲突时保留原文件并说明合并方案。
- 新建可运行项目和仅引入规范是不同范围，按用户选择完成；脚本未创建的业务构建、依赖和启动配置不能冒充已完成。
- 初始化结束前必须启动所涉及的前端、后端并验证页面或接口；后端必须实际运行质量、编译、架构门禁并验证 hook 执行。手动 hook 调用与 Codex 自动触发分别报告；未信任时提醒用户审查，禁止自动授信。服务未启动、检查失败或仍有阻塞时不得宣称全部完成。

若规范目录不存在，先检查用户是否提供了替代路径；否则说明缺少依赖并询问规范位置，禁止使用失效路径继续初始化。
