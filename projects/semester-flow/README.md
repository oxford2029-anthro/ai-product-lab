# Semester Flow｜个人学期工作流

> An AI-assisted semester planning and reflection system built with GPT and Codex.

这是一个以个人真实需求为基础，通过 GPT 与 Codex 协作完成的学期管理 Web 原型。

项目希望把课程、待办事项、每日提醒、弹性工作和每日总结整合到同一个工作流中，减少学期中反复整理课表和任务的认知负担。

## 1. 项目背景｜Background

每个学期的信息通常分散在多个地方：

- 学校课程表
- Apple Calendar
- 临时待办事项
- 志愿工作安排
- 每日学习目标
- 学校活动和截止日期
- 每日总结与反思

传统日历可以记录时间，但很难同时处理以下情况：

- 不同教学周的课程安排
- 不需要每周参加的特殊 Lecture
- 需要排除的过期课程
- 可以灵活安排的工作任务
- 没有完成时需要顺延的待办
- 每天早晚两个固定的计划与总结节点

因此，我尝试设计一个更符合个人学期节奏的工作流。

## 2. 核心需求｜Core Requirements

项目根据我的真实学期安排设计，主要需求包括：

- 每天 8:30 显示今日课程和待办
- 每天 22:00 进行当日总结
- 自动生成每周课程安排
- 支持未完成任务顺延
- 区分固定课程和弹性工作任务
- 排除已经结束或不属于本学期的课程
- 处理只在特定教学周出现的课程
- 跳过 mid-semester break
- 将重要日程导出到 Apple Calendar
- 通过固定视觉区块突出当天最重要的事项

## 3. 产品结构｜Product Structure

当前原型由四个主要页面组成：

### Today

展示：

- 今日课程
- 今日最重要事项
- 待完成任务
- 弹性工作安排
- 晚间总结入口

### Week

展示一周课程、工作与重要截止日期，并根据教学周自动调整安排。

### Tasks

管理不同优先级的任务，并支持未完成任务顺延到下一天。

### Reflection

记录每天完成的事项、未完成原因、精力状态和次日调整。

## 4. 技术方案｜Technical Approach

当前原型使用：

- React
- Vite
- TypeScript
- Local Storage
- ICS calendar export
- GPT for requirement analysis and product planning
- Codex for code generation, debugging and iteration

当前版本优先采用本地数据存储，不涉及用户账户或云端数据库。

## 5. AI 协作开发流程｜AI-assisted Workflow

这个项目不是通过一句提示词一次性生成，而是分阶段完成：

1. 向 GPT 描述真实的课程、任务和生活安排
2. 将零散需求整理为产品功能和约束
3. 确认页面结构、数据逻辑和优先级
4. 将需求拆分为较小的开发任务
5. 使用 Codex 创建项目结构并实现功能
6. 检查页面结果和代码改动
7. 根据实际使用体验继续调整
8. 记录产品决策、错误和下一轮迭代方向

## 6. 关键产品决策｜Key Product Decisions

### Web-first, calendar-supported

网页是主要工作空间，Apple Calendar 负责时间提醒，而不是把所有任务都塞进日历。

### Fixed schedule and flexible workload

课程属于固定时间安排；志愿工作和个人项目更适合作为可以在一周内灵活完成的工作包。

### Human confirmation before automation

学校活动和外部信息可以由系统辅助发现，但不应该未经确认自动加入个人日程。

### Reflection as part of planning

每日总结不是额外功能，而是第二天任务调整和工作流迭代的一部分。

## 7. 我在项目中的角色｜My Role

在这个项目中，我负责：

- 定义真实使用场景
- 梳理产品需求
- 决定功能优先级
- 设计工作流和信息结构
- 向 GPT 和 Codex 提供任务指令
- 检查生成结果
- 测试功能是否符合实际需求
- 记录限制并提出后续迭代方向

AI 主要承担代码生成、结构建议和调试辅助；产品判断和最终验证由我完成。

## 8. 当前状态｜Current Status

当前项目处于早期原型阶段。

已经完成或正在测试：

- 基础页面结构
- 学期课程数据
- Today / Week / Tasks / Reflection 工作流
- 本地任务记录
- Calendar 导出逻辑

下一步计划：

- 测试任务顺延逻辑
- 优化重要事项的视觉层级
- 添加更清晰的教学周设置
- 完成移动端适配
- 记录一周真实使用反馈

## 9. 初步反思｜Initial Reflection

这次实践让我意识到，vibe coding 的核心并不是让 AI 一次生成完整产品，而是：

- 能否准确描述真实问题
- 能否把需求转化为可执行规则
- 能否识别 AI 对需求的误解
- 能否检查和验证生成结果
- 能否在使用过程中持续迭代

在这个项目中，最困难的部分并不是页面本身，而是如何将课程周次、例外安排、任务顺延和提醒机制转化为明确的数据逻辑。

这也说明，AI 降低了代码实现的门槛，但没有替代产品定义、情境理解和判断能力。
