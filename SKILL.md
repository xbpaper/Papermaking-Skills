# 制浆造纸行业专业知识库

一套全面的制浆造纸行业知识库，专注于工艺、浆水平衡计算、物料计算等核心内容。

## 快速开始

### 方式零：一键安装到 Claude Code（最快）

npx skills add your-username/papermaking-skill

### 方式一：直接阅读知识库

进入 knowledge/ 目录，按需阅读：

### 方式二：部署为 OpenClaw Skills（推荐·接入微信）

```bash
# 1. 克隆仓库
git clone https://github.com/xbpaper/Papermaking-Skills.git
cd papermaking-skill

# 2. 安装到 OpenClaw
openclaw skills install ./skills/papermaking-mentor.skill

# 3. 验证安装
openclaw skills list
```

### 方式三：导入 RAG 平台

将 knowledge/ 下所有 .md 文件导入你的RAG系统，使用 prompts/system_prompt.md 作为系统提示词。

## 项目结构

```
papermaking-skill/
├── README.md
├── SKILL.md                     # npx skills 可直接添加
├── CONTRIBUTING.md
├── LICENSE                      # CC BY 4.0（知识内容）
├── LICENSE-CODE                 # MIT（代码部分）
│
├── skills/
│   └── papermaking-mentor.skill # OpenClaw 可直接安装的 skill
│
├── knowledge/
│   ├── pulping/                 # 制浆知识库
│   │   ├── 00_pulping_process.md
│   │   ├── 01_pulp_balance.md
│   │   ├── 02_material_calculation.md
│   │   └── 03_equipment_operation.md
│   ├── papermaking/             # 造纸知识库
│   │   ├── 00_papermaking_process.md
│   │   ├── 01_water_balance.md
│   │   ├── 02_material_calculation.md
│   │   └── 03_equipment_operation.md
│
├── prompts/
│   └── system_prompt.md         # AI顾问系统提示词
│
├── deploy/
│   └── DEPLOY.md                # 完整部署指南
│
└── .github/
    ├── ISSUE_TEMPLATE/
    └── workflows/validate.yml   # PR自动验证
```

## 核心框架：决策顺序

1. **先定可行集**
   → 根据产能确定实际可采用的设备和工艺参数
   → 特殊工艺（废纸浆、漂白）优先核查
2. **目标倒推**
   → 先问"最终产品质量要求是什么"
   → 再选能达到这个目标的最短路径
3. **行业标准校正**
   → 核查每个候选工艺的行业标准和环保要求

## 输出规范：最多3个选项 + 明确切换条件

→ "产能为X时选A，产能不足选B"
→ 不给模糊备选清单

## 许可证

知识内容（knowledge/、prompts/）：CC BY 4.0 — 署名即可自由使用、修改、分发
代码（skills/、deploy/、.github/）：MIT
