# 代运营视频（agency-video）

给代运营客户做 AI 剧情 / 带货短视频的 skill：从出点子、写分镜、出参考图，到生成视频、审片、粗剪，按固定流程一步步带着做。恐怖、喜剧、狗血、悬疑、科幻、温情、ins 风氛围片都能用；每个品牌的口径单独放在 `brands/` 里。

原名「餐馆剧情（restaurant-drama）」，最早给 Naturestaurant 做；现在 NRT 是 `brands/nrt/`，用法不变。

适用于 Codex 和 Claude Code。

## 安装

```bash
git clone https://github.com/skylar-33/agency-video.git ~/.agents/skills/agency-video
```

然后新建一个空文件夹，在里面打开 Codex，输入 `/skills`，列表里出现 `agency-video` 就装好了。

更新：`cd ~/.agents/skills/agency-video && git pull`

## 怎么用

```
$agency-video NRT：做一条恐怖题材的抓马视频，道具用官网的纸杯
$agency-video 圣诞树：做一条 ins 风开箱氛围片
```

先说是哪个品牌（`brands/` 里的文件夹），然后会按这个顺序推进，每一步做完等你点头再往下走：

0. 确认品牌和这次的需求
1. 出 6–9 个点子让你挑
2. 写分镜（角色、道具、每段几秒、配乐怎么接）
3. 出角色、道具、场景参考图（品牌配置可以设成跳过）
4. 每段出首帧
5. 生成视频并自动审片
6. 粗剪出片

## 规则放在哪

- 所有品牌都要守的：[`references/platform-rules.md`](references/platform-rules.md)（TikTok 红线、商品真实性、发布前检查）
- 每个品牌自己的：`brands/<品牌>/brand.md`（品牌名念法、网址、CTA、商品事实、表达限制、活动、画布、风格偏好）

| 品牌文件夹 | 品牌 |
| --- | --- |
| `brands/nrt/` | Naturestaurant 餐饮包装 |
| `brands/easybuy-xmas/` | EZ Easybuy Choice 4.5ft 植绒预装灯圣诞树 |

新品牌按 [`brands/README.md`](brands/README.md) 的模板建。

## 需要准备

- 出海匠画布：出海匠 API Key（找项目负责人要，交给 Codex 帮你配）
- Brigo · EI 画布：打开 hypit（易播星）并连上 MCP
- `python3`、`ffmpeg`（审片和粗剪要用，没装的话让 Codex 装）

## 里面有什么

| 位置 | 内容 |
| --- | --- |
| `SKILL.md` | 流程主文件，Codex 读这个 |
| `brands/` | 各品牌配置、商品数据、产品参考图、模特库（NRT 的 6 人三视图在 `brands/nrt/`） |
| `references/` | 平台红线、速查表、提示词格式、画布踩坑记录 |
| `scripts/` | 出海匠画布搭建、批量生成、动线标注、审片、粗剪 |
| `vendor/` | 收录的两份第三方导演 skill 原文（MIT，保留原许可） |
