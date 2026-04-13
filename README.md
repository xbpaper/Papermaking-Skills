# 制浆造纸行业专业技能skill

这是一套完全开源的制浆造纸行业专业技能skill，专注于工艺、浆水平衡计算、物料计算等核心内容，分为制浆和造纸两个主要模块。

## 项目目标

制浆造纸行业工程师每天面临大量技术问题，尤其是在工艺优化、浆水平衡计算、物料计算等方面。本项目旨在：

- 提供专业、准确的行业知识
- 一键部署为 OpenClaw Skills，接入微信/企业微信/QQ，让行业从业者用熟悉的方式获得AI顾问服务
- 导入任意RAG平台（Dify、FastGPT、RagFlow等）构建专业问答机器人

核心差异：本项目不只是数据工具，而是一套决策框架——帮助行业从业者用正确的思维顺序解决实际生产问题。

## 快速开始

### 方式零：一键安装到 Claude Code（最快）

npx skills add xbpaper/papermaking-skill

### 方式一：直接阅读知识库

进入 knowledge/ 目录，按需阅读：

#### 制浆部分

- 00_pulping_process.md - 制浆工艺详解
- 01_pulp_balance.md - 浆水平衡计算
- 02_material_calculation.md - 物料计算
- 03_equipment_operation.md - 设备操作与维护

#### 造纸部分

- 00_papermaking_process.md - 造纸工艺详解
- 01_water_balance.md - 水平衡计算
- 02_material_calculation.md - 物料计算
- 03_equipment_operation.md - 设备操作与维护

### 方式二：部署为 OpenClaw Skills（推荐·接入微信）

```bash
# 1. 克隆仓库
git clone https://github.com/xbpaper/papermaking-skill.git
cd papermaking-skill

# 2. 安装到 OpenClaw
openclaw skills install ./skills/papermaking-mentor.skill

# 3. 验证安装
openclaw skills list
```

部署后在微信/企业微信中 @机器人 直接对话即可。详见 部署指南。

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
   → 用产能+原料确定实际可采用的工艺和设备
   → 特殊工艺（废纸浆、漂白）优先核查
2. **目标倒推**
   → 先问"最终产品质量要求是什么"
   → 再选能达到这个目标的最短路径
3. **行业标准校正**
   → 核查每个候选工艺的行业标准和环保要求

## 输出规范：最多3个选项 + 明确切换条件

→ "产能为X时选A，产能不足选B"
→ 不给模糊备选清单

## 如何贡献

欢迎以下形式的贡献：纠错、补充工艺/设备分析、贡献实际生产数据、分享真实案例（脱敏处理）。
请参阅 CONTRIBUTING.md。

## 个人网站和公众号

个人网站：[paperfancy.cn](https://www.paperfancy.cn)

微信公众号：纸鸢Paperfancy

## 许可证

知识内容（knowledge/、prompts/）：CC BY 4.0 — 署名即可自由使用、修改、分发
代码（skills/、deploy/、.github/）：MIT
