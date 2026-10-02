# 减少AI痕迹（DeAI Writing Skill）

一个融合双重检测逻辑的 AI 写作痕迹清理技能（Agent Skill）：**去掉机器味，也去掉心虚味。**

- **机器味** = AI 生成文本的统计性习惯。基于 Wikipedia「Signs of AI writing」与 [blader/humanizer](https://github.com/blader/humanizer) v3.1.0 的 26 类模式，按根因分六组（装腔作势 / 节奏靠规则 / 拔高与借权威 / 格式靠规则 / 聊天残留 / 对错误的读者写作），按强度排序、一见即改，并守住「不编造事实」的底线。
- **心虚味** = 学术写作中的防御性写作。基于「发布会原则」：论文是学术发布会，不是项目总结或自我审查报告——不平均展示、不主动示弱、不写实验流水账、不替审稿人攻击自己。

## 与上游项目的区别

| | blader/humanizer | anti-defensive-writing-Skill | 本技能 |
|---|---|---|---|
| 范围 | 通用文本去 AI 味 | 学术论文防防御性 | 两者融合 + 中文对应表达 |
| 模式库 | 26 类（v3.1.0） | — | 完整移植并中文化 |
| 叙事规则 | — | 发布会原则 | 完整移植 |
| 学术终审 | — | 递刀子自查 | 三轮自我质询（AI 破绽 / 改写 / 审稿人视角） |

## 安装

把整个目录拷进你的 skills 目录即可：

```bash
# Claude Code / Kimi Code
cp -r 减少AI痕迹 ~/.claude/skills/
```

或复制 `SKILL.md` 内容到你的 Agent 自定义指令 / System Prompt 中直接使用。

## 使用

对 Agent 说：

```
用减少AI痕迹帮我改改这段文字：[文本]
```

学术论文场景会自动追加防御性写作审查；也可以点名：

```
用减少AI痕迹过一遍我的摘要和结论，重点检查有没有替审稿人递刀子。
```

## 文件

- `SKILL.md` — 技能本体（模式库 + 发布会原则 + 声音注入 + 终审流程）

## 来源与许可

- 模式库基于 [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)（WikiProject AI Cleanup 维护），结构移植自 [blader/humanizer](https://github.com/blader/humanizer) v3.1.0（MIT）
- 发布会原则改写自 [Adkid-Zephyr/anti-defensive-writing-Skill](https://github.com/Adkid-Zephyr/anti-defensive-writing-Skill)（MIT）
- 融合与改写：hzhuan717，以 [MIT](LICENSE) 协议发布

如果它让你的文字更像人写的，给个 ⭐ 让更多人找到它。
