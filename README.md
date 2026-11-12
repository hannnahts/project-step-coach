# Project Step Coach

**把“这一步做完了”变成“我真正学会了”。**

`project-step-coach` 是一个 Codex skill：当项目完成一个有意义的功能、设计决策或阶段时，它会基于当前项目内容，用老师的方式讲清原理和术语，补上产品级思考，并用三道模拟面试题检验理解。

## 它会做什么

一次复盘包含四部分：

1. **本环节完成**：简要说明结果与范围。
2. **原理与术语**：用因果关系解释关键机制，并解释必要的术语。
3. **产品级思考**：联系用户需求、体验、成功标准和相关取舍，指出有价值的下一步。
4. **模拟面试：三题**：围绕概念、设计取舍和实际场景各出一道题，不提前给答案或提示。

如果你回答面试题，skill 会逐题反馈推理与知识缺口，并给出更完整的示范回答。

## 适合什么时候用

- 一个功能或项目阶段刚完成，想知道实现背后的原理。
- 想把“改了什么”进一步讲成“为什么这么设计、对用户有什么影响”。
- 想练习解释项目经验和回答技术面试问题。

它不会在项目还没做完时打断工作，也不适合每条命令完成后都触发。

## 安装

Codex skill 是一个包含 `SKILL.md` 的独立文件夹。可以按个人使用或单个项目选择安装位置；安装后在新的 Codex 会话里调用。

### 个人安装

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/hannnahts/project-step-coach.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/project-step-coach"
```

### 只在当前项目使用

在项目根目录运行：

```bash
mkdir -p .agents/skills
git clone https://github.com/hannnahts/project-step-coach.git \
  .agents/skills/project-step-coach
```

也可以把仓库文件夹下载后，手动复制到对应的 skills 目录。Codex 的技能格式与目录结构可参考 [OpenAI Skills 文档](https://developers.openai.com/plugins/concepts/skills)。

## 使用

完成一个项目环节后，可以直接显式调用：

```text
$project-step-coach 请复盘刚完成的项目环节。
```

如果当前对话已经包含代码、设计决策和完成结果，skill 会据此讲解。上下文不足时，它会停留在已知事实，必要时只追问一个关键问题。

## 演示样例

查看[筛选与分页功能复盘样例](examples/sample-session.md)。它展示了 skill 如何围绕一个完成的功能讲解原理、提出产品问题并出三道面试题。该样例是虚构的演示场景，不是用户反馈或效果数据。

## 范围与许可

这个 skill 提供学习和复盘引导，不替代项目代码审查，也不会在缺少上下文时假设项目实现细节。

仓库目前尚未声明开源许可证。公开可见不等于已授予转载、修改或再分发许可；如需这些权限，请先联系作者确认。
