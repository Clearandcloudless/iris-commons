# Iris Commons

> **Ideas without borders. 思想无界，自由相连。**

**Iris Commons（虹桥思想共同体）** 是一个开放、公益的人类—AI协作研究项目。

“Iris”取自希腊神话中的彩虹信使：彩虹连接彼此分隔的世界，也保留每一种颜色。这个项目希望让思想跨越语言、地域、学科、身份和模型平台的边界，在保留原意与差异的前提下自由流动、共同演化。

本仓库不是一个已经定型的软件产品，而是用于共同讨论、设计、论证和试验的公共空间。

## 我们想解决什么问题

今天，人们可以分别与 GPT、Gemini、本地模型和其他智能体深入交流，但这些交流通常：

- 被封闭在不同平台和账号中；
- 难以迁移、引用、复核和长期积累；
- 受到语言、专业背景和表达方式的限制；
- 很难转化为多人共同维护的公共知识；
- 缺少对人类贡献、AI参与、翻译过程和证据来源的清晰记录。

Iris Commons 探索一种新的协作模式：

1. 每个人使用自己的语言与自己的 AI 秘书交流；
2. AI 帮助整理、翻译、检索、质疑和结构化表达；
3. 人类选择哪些内容进入公共协作空间；
4. 参与者通过 Issue、Pull Request 和版本记录共同修改知识；
5. 重要观点始终保留原文、来源、参与者和审核状态；
6. 不同模型可以参与，但不能绕过人类授权和治理。

## 当前阶段：GitHub-only MVP

第一阶段只使用 GitHub，验证最小可行协作闭环：

```text
个人思考 / 人机对话
        ↓ 人工选择
      提交 Issue
        ↓
翻译、讨论、质疑、补证
        ↓
形成提案 / 文档 / 实验记录
        ↓ Pull Request
      同行审查
        ↓ 人类批准
   进入公共知识库
```

GitHub 在这一阶段承担：

- 公共讨论入口；
- 可版本化的知识文档；
- 提案、审查和决策记录；
- 贡献归属和变更历史；
- 未来协议与原型代码的协作空间。

GitHub **不被视为**最终的数据湖、隐私档案库、科研计算平台或永久保存机构。

## 项目原则

### 1. 原文优先

翻译、摘要和改写都是派生内容，不能覆盖原始表达。参与者应能追溯“谁在何时、以什么语言、表达了什么”。

### 2. 人类最终负责

AI 可以起草、翻译、整理、检索和审查，但不能独立：

- 公开私人或敏感信息；
- 批准关键研究结论；
- 代表他人作出授权；
- 绕过审查修改受保护内容。

### 3. 差异不是噪声

Iris Commons 不追求把所有观点压缩成单一结论。合理分歧、少数意见、条件差异和不确定性都应被保留。

### 4. 可追溯与可复核

重要主张应尽量关联：

- 原始来源；
- 人类贡献者；
- AI模型与参与方式；
- 翻译或转换过程；
- 数据、代码和环境版本；
- 当前可信状态。

### 5. 开放但有边界

公益和开放不等于公开一切。隐私、版权、科研伦理、安全风险和第三方权利优先于自动公开。

### 6. 多模型与平台中立

项目不绑定某个模型厂商、云平台或专有协议。优先采用 Markdown、YAML、JSON、Git 和开放接口等可迁移格式。

## 参与方式

当前最需要的不是大量编码，而是共同论证：

- 这个构想是否真正解决了协作障碍？
- GitHub 是否适合承担第一阶段公共空间？
- 多语言内容应该如何组织？
- AI秘书应拥有多大权限？
- 如何处理错误、偏见、提示注入和恶意参与？
- 如何记录贡献和建立可信度？
- 哪个真实公益课题适合作为首个试验？

请阅读：

- [愿景与边界](VISION.md)
- [治理规则](GOVERNANCE.md)
- [参与指南](CONTRIBUTING.md)
- [路线图](ROADMAP.md)
- [初始架构](ARCHITECTURE.md)
- [AI秘书协议草案](docs/ai-secretary-protocol.md)
- [研究记录模型](docs/research-record-model.md)
- [威胁模型](docs/threat-model.md)

## 仓库结构

```text
.
├── README.md
├── VISION.md
├── ARCHITECTURE.md
├── GOVERNANCE.md
├── CONTRIBUTING.md
├── ROADMAP.md
├── CODE_OF_CONDUCT.md
├── LICENSE
├── LICENSE-DOCS.md
├── docs/
│   ├── ai-secretary-protocol.md
│   ├── research-record-model.md
│   └── threat-model.md
└── .github/
    ├── ISSUE_TEMPLATE/
    └── pull_request_template.md
```

## 项目状态

**概念验证 / 公开论证阶段。**

当前所有核心设计均为草案，可以通过 Issue 和 Pull Request 修改。

## License

- 软件代码：MIT License
- 原创文档与研究材料：CC BY 4.0
- 数据集、模型、第三方材料：以各自明确标注的许可证为准

---

## English summary

Iris Commons is an open, nonprofit-oriented research initiative exploring borderless collaboration between people and AI assistants. It aims to preserve original voices while enabling translation, structured debate, evidence review, versioned knowledge, and accountable human governance across languages, disciplines, regions, and model platforms.
