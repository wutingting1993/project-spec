# Project Spec

通用项目规范模板与项目初始化技能。可用于为已有项目接入规范与质量检查，也可生成 Java 分层骨架和通用类。

## 仓库目录

```text
project-spec/
├── spec/                   项目规范与日常质量工具
│   ├── docs/standards/     前后端规范
│   ├── config/             代码风格配置
│   ├── scripts/            质量检查脚本与 Java 模板
│   ├── tools/              质量与架构检查工具
│   ├── tests/              质量工具测试
│   └── .codex/             Codex Hook 配置与脚本
└── skills/
    └── project-init/       项目初始化技能
        ├── SKILL.md        技能入口
        ├── INIT.md         初始化指南
        ├── scripts/        初始化脚本
        └── tests/          初始化测试
```

初始化脚本从同一仓库的 `spec/` 读取模板。接入后的项目可直接使用复制过去的规范和质量工具。

## 初始化

从本仓库根目录运行以下命令，将目标路径和基础包名替换为项目实际配置。

```bash
bash skills/project-init/scripts/init-project.sh /path/to/project \
  --base-package com.example.orders
```

目标项目布局、已有文件冲突和验收步骤见[初始化指南](skills/project-init/INIT.md)。如需在 Codex 中使用该技能，参见[技能说明](skills/project-init/SKILL.md)。
