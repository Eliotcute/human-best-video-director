# 人类最强编导

一套面向短视频与新媒体内容工作的 Agent Skills。它先理解用户真正要完成的任务，把泛化需求整理成可执行任务，再根据交付范围调用对应的专项 Skill。

适用于账号定位与起号、IP 与创始人故事、选题、钩子、脚本制作、发布复盘及编导训练。

## 核心能力

- 将自然语言需求整理成可执行、可交接、可验收的任务
- 信息不足时只询问会改变方案的关键问题
- 信息充分时直接执行，避免重复问诊
- 根据任务范围组合多个专项 Skill
- 默认提供一个首选方案，不用数量代替判断
- 区分事实、假设和未经验证的结论
- 根据平台、账号阶段、素材和生产限制调整方案
- 对照用户原始目标验收最终交付

## Skill 组成

| Skill | 职责 |
|---|---|
| `human-best-video-director` | 总入口：需求编译、任务路由和最终验收 |
| `hbvd-intake` | 识别真实需求，补充关键信息并形成任务合同 |
| `hbvd-account` | 账号定位、关注理由、内容支柱和起号实验 |
| `hbvd-ip` | IP 定位、信任建立和创始人故事 |
| `hbvd-topic` | 选择当前最值得执行的选题 |
| `hbvd-hook` | 标题、封面、首屏、开头和正文兑现链路 |
| `hbvd-script` | 口播、图文、镜头、素材和拍摄执行方案 |
| `hbvd-review` | 内容审稿、数据诊断和单变量复盘实验 |
| `hbvd-training` | 编导能力训练、素材调用和前后对照验收 |

每个目录都是一个可独立调用的 Skill，其中 `human-best-video-director` 负责根据任务选择和组合其他专项 Skill。

## 安装

将九个 Skill 目录复制到 Codex Skills 目录：

```bash
mkdir -p ~/.codex/skills
cp -R human-best-video-director hbvd-* ~/.codex/skills/
```

重新打开 Codex 任务后，即可通过 `$human-best-video-director` 调用总入口，也可以直接调用某个专项 Skill。

## 推荐用法

不确定应该调用哪个专项 Skill 时，使用总入口：

```text
使用 $human-best-video-director，先判断我的真实需求，再帮我制定一个小红书新账号的起号方案。
```

信息不足时，它会先询问最多三个关键问题；信息充分后，会继续完成当前请求，不需要用户逐阶段重复下令。

### 账号起号

```text
使用 $human-best-video-director。我准备做一个不出镜的小红书 AIGC 账号，目标用户是普通职场人和新媒体运营。我擅长商业化落地和内容创作，请给我一个账号定位、一个首选题和一份可拍摄脚本。
```

### 已有选题，直接写脚本

```text
使用 $human-best-video-director。小红书新账号，受众是第一次买房的上班族。选题是“售楼处说离地铁800米，我在下班高峰实际走一遍”。不出镜，有地图和实拍录像，请写一版60秒旁白和拍摄清单。
```

### 内容数据复盘

```text
使用 $human-best-video-director，根据这条内容、账号基线和发布数据判断主要问题，并设计下一轮只修改一个变量的验证方案。
```

## 工作方式

```text
用户需求
  → 判断信息是否充分
  → 必要时询问关键问题
  → 编译为内部任务合同
  → 调用所需专项 Skill
  → 继承前序事实与结论
  → 整合交付并验收
```

内部任务合同不会默认展示给用户。最终输出以用户能直接理解和使用的内容为准，而不是展示路由或诊断过程。

## 使用边界

- 不虚构身份、经历、案例、数据和用户评价
- 不承诺爆款、涨粉、收入或平台推荐结果
- 关键事实不足时，会追问、明确假设或停止不可靠的推断
- 平台经验与用户事实分开表达
- 数据不足时只提出假设，不把相关性写成因果关系
- 钩子必须能够被正文和真实证据兑现

## 目录结构

```text
human-best-video-director-release/
├── README.md
├── human-best-video-director/
├── hbvd-intake/
├── hbvd-account/
├── hbvd-ip/
├── hbvd-topic/
├── hbvd-hook/
├── hbvd-script/
├── hbvd-review/
└── hbvd-training/
```

每个 Skill 目录包含：

```text
SKILL.md
agents/openai.yaml
```
