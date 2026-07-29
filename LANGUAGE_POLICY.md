# Language Policy / 语言规则

状态：`draft-0.1`

Iris Commons 不要求参与者使用同一种语言。语言规则的目标不是建立新的英语门槛，而是同时满足：

- 人能够使用最准确、最自然的语言表达；
- AI和软件能够稳定解析、交换和迁移项目数据；
- 原文、译文、摘要和规范版本之间的关系清楚可追溯。

## 1. 总体原则

> **English for interoperability; native languages for thought.**  
> **英文负责互操作，母语负责思想表达。**

这意味着：

- 人类思想和讨论不受语言限制；
- 机器可读标识采用稳定英文；
- 翻译负责连接不同语言，而不是取代原文；
- 英文摘要可以作为公共桥梁，但不能成为参与前提；
- 语言质量和英语熟练程度不得被当作观点可信度。

## 2. 内容语言分层

### 2.1 参与者原始表达

Issue、评论、提案、访谈记录和研究观点可以使用任何语言。

原始表达是该参与者观点的权威版本。AI或他人不得仅保留改写、摘要或翻译后删除原文。

### 2.2 翻译与摘要

译文和摘要属于派生内容，应尽量记录：

```yaml
source_language: zh-CN
target_language: en
translation_method: ai
translation_provider: OpenAI
translation_model: model-name-or-unknown
human_reviewed: false
source_reference: issue-or-file-reference
source_revision: commit-or-timestamp
```

机器翻译必须标明。无法准确转换的术语应保留原词并附解释。

译文不得：

- 把疑问改写成事实；
- 把暂定推断改写成确定结论；
- 删除少数意见或条件限制；
- 用更符合目标语言文化的立场替换原意；
- 在没有原作者确认时宣称“语义完全一致”。

### 2.3 技术规范

涉及协议实现、数据模式、API、状态枚举和机器互操作的规范，长期目标是：

- 英文版本作为协议规范版本；
- 其他语言作为明确关联的翻译版本；
- 每个翻译版本标注源文件、源commit和同步状态；
- 出现协议解释冲突时，以标记为normative的规范版本为准。

这项规则仅决定软件和协议语义，不改变参与者原始观点的权威语言。

当前仓库仍处于中文起草阶段。现有中文文档继续有效，英文规范版将逐步通过Pull Request建立，不要求一次性重写全部内容。

## 3. 必须使用英文的机器标识

以下内容使用小写英文或约定的英文格式：

- repository、branch、directory和file名称；
- YAML、JSON和表单字段ID；
- API参数和Schema属性；
- label名称；
- 状态、类型和角色枚举；
- commit类型前缀；
- 工具名称和协议标识。

示例：

```yaml
record_type: proposal
source_language: zh-CN
translation_status: machine-generated
knowledge_status: discussing
human_reviewed: true
```

不建议：

```yaml
记录类型: 提案
原始语言: 中文
审核状态: 已审核
```

显示给用户的标签和说明可以双语，但稳定ID不得随界面语言变化。

## 4. README与入口文件

- 根目录 `README.md` 是项目宣传与兴趣入口，可使用中英双语；
- `README.md` 不承担完整规范、配置和治理说明；
- AI参与方法集中在 `AI_PARTICIPATION.md`；
- AI自动发现和行为要求集中在 `AGENTS.md` 及各客户端指令文件；
- 正式技术规范放在 `docs/` 或未来的 `specs/` 目录；
- 多语言完整译文应使用语言后缀或独立目录，例如：

```text
specs/research-record.md
translations/zh-CN/research-record.md
translations/ja/research-record.md
```

翻译文件应在顶部标注：

```yaml
translation_of: specs/research-record.md
source_commit: abc1234
translation_status: reviewed
```

## 5. Issue与Discussion

- 允许任何语言直接提交；
- 表单底层字段ID使用英文；
- 字段显示名称优先采用中英双语，后续可扩展更多语言；
- `source_language` 必填；
- 英文摘要是推荐项而不是必填项；
- AI可以按需生成桥接摘要；
- 不得仅因缺少英文版本关闭或降低Issue优先级。

建议内容结构：

```markdown
## Original / 原文

参与者原始内容。

## Bridge summary / 桥接摘要

可选的英文或其他公共桥接语言摘要。

## Translation notes / 翻译说明

术语、语境、歧义和人工修订状态。
```

不要求每条短评论机械重复全部结构。发生语义争议、正式提案或跨语言审查时应使用明确分层。

## 6. Pull Request

PR正文至少说明：

- `source_language`；
- 是否包含翻译；
- 翻译方式；
- 哪个版本属于规范内容；
- 原作者或审查者是否确认译文；
- AI是否参与翻译、起草或审查。

只修改译文的PR不得在未声明的情况下改变规范语义。

## 7. AI助手行为

AI助手必须：

1. 使用用户当前语言与用户交流；
2. 不要求用户为了参与而先翻译成英文；
3. 保留用户原始表达；
4. 为机器字段、路径和标签使用英文；
5. 对外发布时区分原文、译文、摘要和推断；
6. 对存在歧义的翻译主动询问原作者或标注不确定性；
7. 不因英语表达更流畅而赋予其更高可信度；
8. 在用户需要跨语言参与时主动提供桥接摘要和术语说明；
9. 记录AI翻译或改写角色；
10. 不把自己的重写冒充用户原话。

## 8. 语言代码

使用BCP 47风格语言标签，例如：

```text
en
zh-CN
zh-TW
ja
ko
es
ar
```

不确定时可以使用：

```text
und
```

不要仅填写模糊的“中文”“外语”或“other”而不保留更具体说明。

## 9. 同步状态

翻译文档建议使用以下状态：

- `machine-generated`：机器生成，尚未人工检查；
- `human-reviewed`：已进行人工语言审查；
- `author-confirmed`：原作者确认关键语义；
- `outdated`：源版本已有更新；
- `partial`：仅翻译部分内容；
- `withdrawn`：因严重错误不再使用。

## 10. 冲突处理

### 参与者观点冲突

以参与者的原始语言内容为判断其意图的首要依据，并邀请原作者确认。

### 协议实现冲突

以明确标记的normative规范版本和对应commit为准。

### 译文长期未同步

不得静默展示为最新版本，应标注 `outdated` 并链接源版本。

## 11. 过渡计划

当前阶段按以下顺序推进：

1. 保持现有中文文档可用；
2. 所有新增机器标识使用英文；
3. README保持简短双语项目入口；
4. Issue和PR模板改为双语显示、英文ID；
5. 优先翻译AI接入、治理和核心协议；
6. 建立自动检查，识别缺失语言字段和过期译文；
7. 根据真实跨语言试验结果修订本规则。

语言政策本身也必须接受不同语言参与者的审查，不能只由英语或中文使用者决定。