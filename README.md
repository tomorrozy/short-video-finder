# short-video-finder

一个 WorkBuddy Skill：在抖音、小红书等平台按指定类型搜索短视频，整理成带标题、作者、简介、链接的清单，并在内容创作场景下附「可借鉴点」拆解。

## 功能

- 按类型/主题检索短视频，默认 8–10 条，可指定数量与平台
- 平台路由：抖音走 web 检索 `site:douyin.com/video`（无专用渠道），小红书/B站/YouTube 走 `agent-reach` 专用渠道
- 逐条核验链接有效性，剔除不符项；作者/时长/点赞等缺失字段如实标注「未显示」，不编造
- 内容创作场景附「可借鉴点」与「套路小结」；批量任务（≥30 条）导出 CSV + Markdown 并标注合规等级与核验方式
- 内置平台限流（web read / web search）的降级处理经验

## 安装

把本仓库的 `SKILL.md` 放到 WorkBuddy 用户级技能目录：

```text
~/.workbuddy/skills/short-video-finder/SKILL.md
```

（Windows 对应 `C:\Users\<用户名>\.workbuddy\skills\short-video-finder\SKILL.md`）

重启 WorkBuddy 后即可使用。触发方式：直接说「找几个抖音上的美食探店短视频」「找 XX 类爆款视频做参考」。依赖 `agent-reach` 技能提供小红书/B站/YouTube 渠道；抖音走公开网页检索，无额外依赖。

## 文件

- `SKILL.md` — 技能定义（触发条件、平台路由、工作流程、输出格式、注意事项）

## 许可与说明

技能本身可自由使用。检索结果来自公开网页，版权归原作者与平台所有；请遵守目标平台的使用条款。技能仅整理公开可见的文案与链接，不下载、不转载视频内容。
