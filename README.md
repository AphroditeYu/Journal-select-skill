# Journal Select Skill

面向中文与英文论文的可复用选刊 Skill。将论文匹配、官方证据与作者硬条件结合，输出候选比较和投稿顺序。

## 设计

**论文画像 → 候选发现 → 官方核验 → 硬条件过滤 → 匹配与权衡 → 投稿顺序。**

- 不把影响因子等同于 SCIE/SSCI 收录，不把 JCR 分区与其他分区混用。
- 动态信息记录来源、核验日期和适用年份；关键未知项单独列出。
- 不预存易过期的期刊白名单、费用表或 AI 政策结论。
- 不预测录用率，不自动投稿、付费或向第三方上传研究材料。
- 支持探索候选、个性化推荐、指定期刊比较和投稿前复核。

## 仓库结构

```text
skills/journal-select/
  SKILL.md
  agents/openai.yaml
  references/evidence.md
  references/selection.md
  references/acceptance-cases.md
  assets/report-template.md
```

## 安装到 Codex

把 `skills/journal-select` 整个文件夹复制到自己的 `$CODEX_HOME/skills/`；未设置 `CODEX_HOME` 时通常为 `~/.codex/skills/`。安装后的入口应是 `skills/journal-select/SKILL.md`，不要再多嵌套一层仓库目录。重新打开会话使环境发现新 Skill。

仓库地址：https://github.com/AphroditeYu/Journal-select-skill

该 Skill 使用可用的网页检索工具；没有联网能力时只能提供暂定建议和待核实清单。数据库订阅、付费访问及机构目录不会由 Skill 自动获得。无需配置 API 密钥或运行专用脚本。

## 使用示例

```text
使用 $journal-select 辅助选刊。
题目：我的论文题目
摘要：我的论文摘要
文章类型：实证研究
硬条件：必须为 SSCI；学校适用目录另附
预算：总费用不超过 10000 元人民币
期限：希望六个月内接收（请判断风险，不承诺）
偏好：主题匹配优先，其次时间
请给出 3–5 本候选，附官方来源、核验日期和投稿顺序。
```

也可以说：`使用 $journal-select 比较我列出的三本期刊，重点核对收录、费用和 AI 使用要求。`

不要在 GitHub issue 或公开提交中粘贴未发表全文、原始数据、个人信息或登录凭据。个人选刊报告应放在仓库之外。

## 维护与验证

版本：0.1.0。入口和 UI 元数据保持一致；更新时检查内部链接，并用 `references/acceptance-cases.md` 中的场景验证行为。若环境提供 skill-creator，可运行其 `scripts/quick_validate.py` 检查 Skill 结构。

结构校验不证明推荐质量。真实选刊仍需当前官方信息与用户所在单位要求。仓库不包含真实用户稿件、数据库导出内容或预置期刊推荐结论。

当前未指定开源许可证；仓库所有者可按实际意愿另行选择并添加 LICENSE。
