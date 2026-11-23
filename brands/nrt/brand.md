# 品牌配置：Naturestaurant（NRT）

开工前必读。冲突时本文件优先于 skill 里通用文件的写法（用户当场的话仍然最优先）。通用的平台红线见 `references/platform-rules.md`。

## 一、基本信息

| 项 | 内容 |
| --- | --- |
| 品牌 | Naturestaurant（简称 NRT），餐饮包装 / 一次性餐具官网 |
| 市场 / 平台 | 美国 TikTok |
| 画布 | 出海匠画布（用 `scripts/` 里的脚本，画布名前缀 `NRT · `） |
| 商品来源 | `商品/06-官网商品目录.md`、`商品/官网商品数据/`（抓取 2026-10-19）；项目里有 `knowledge/06-官网商品目录.md` 时以项目为准 |
| 模特 | NRT 专用模特库 `数字人三视图/`：6 人三视图 01 Alex、02 Elena、03 Marco、04 Susan、05 Daniel、06 Carlos，正面图在 `数字人三视图/正面入库图/`；项目里有 `assets/数字人三视图/` 时以项目为准。**优先深肤色**（Elena、Marco、Daniel、Carlos），锁脸只换装；6 人都是成年人。**只给 NRT 用，其他品牌不要拿来用** |
| 样板 | P04 吸血鬼叉子（`assets/P04-吸血鬼叉子/project.json`、`timeline_v2.json`，分镜 `content/分镜/P04-吸血鬼叉子-分镜.md`）；光影样板 V07 婚礼（`content/分镜/V07-设定集.md`、`V07-提示词.md`）；复盘 `knowledge/07-AI视频制作复盘.md`。不在 NRT 项目文件夹里时这些样板没有，按规则做 |

## 二、网址和品牌名（陈尚宇定）

- 视频里不出现网址：口播、台词、字幕、道具、尾板都不说、不写 naturestaurant.com / dot com。
- 剧情里提品牌只说品牌名 Naturestaurant；**结尾 CTA 不说品牌名**，改成引导关注主页（`"Follow for more."`、`"Hit follow — part two's on my page."`、`"Check my profile."`）；画面字幕同理。
- 品牌尾板最好不要；一定要留只闪一下（≤0.5 秒），不放网址和按钮。
- 网址只写在发布文案、图文和文档里，统一写 `https://naturestaurant.com/`（不加 www，保留 https:// 和结尾斜杠）。
- P04 的 `"Grab a case at Nature-stawrant dot com."` 和带网址按钮的尾板是旧做法，新片不再照搬。

## 三、品牌名念法（2026-10-28 陈尚宇定，同日改）

**口播按 "nature restaurant" 念，提示词台词里写 `Nature-restaurant`。**
- 改的原因：`Nature-stawrant` 拼读在 C1 VA / VA3 四个候选里全错（Natural shot it / Natural stutter / Natural starter），模型念 "nature restaurant" 最稳。
- 审片 `review.py --brand natur`：把品牌词单独切出来转写，整句转写不可信；听起来是 "nature restaurant" 就算对，"natural ……" 算错；最终人耳确认。
- 念错只补拍说品牌名的那一镜（挂原视频作视频1 保证音色和光线一致），替换那几秒；有 ElevenLabs 时也可以只替换品牌词音频。
- 品牌台词尽量 ≤6 个词、能看见嘴时用近景；超长拆两镜或改画外。
- 历史记录：Seedance 不听括号里的读音提示；拼读不是稳定解（V02 2026-10-23 "Nature-stawrant dot com" 3 条全错，单独成句再 1 条仍错）。拿不准时品牌词按画外处理，用配音 / 字幕。

## 四、logo

- 要读的字不让 AI 生成；logo 用参考图并逐字母写拼写 N-a-t-u-r-e-s-t-a-u-r-a-n-t，出图后放大核对。
- 「只改某处」的编辑生图也会重画胸口 logo，常拼错（V02 R3：Naturesbiunty / Naturessurant）。编辑后必放大核对；坏了用 ffmpeg 把编辑前那张的 logo 区域羽化贴回，不必重出。

## 五、商品和业务信息

- 出镜商品必须是官网在售款（查 `商品/`）。在售的就可以大胆种草、夸张展示，字幕放开写；规格数字（尺寸、每箱数量）照官网写，不编。
- 价格可以报，用发布前一天的官网实时价，不用注明取价日期。
- 不写配送时效。
- 不提：定制 logo、城市合伙人、佣金和收益。
- 环保说法（Compostable、Recyclable、No PFAS 等）只用在官网详情图明确写了的商品上；目录里标 [推断] 或「未确认」的用途不当卖点。
- 商品目录里的价格是抓取当天标价，会变；写进脚本前用官网实时价。

## 六、抓马模式（陈尚宇的偏好，做「抓马」系列时用）

类型片大脑洞，场景不限餐饮，餐具只当剧情道具；角色在关键时刻顺口说出 Naturestaurant（只说品牌名，不说网址）；结构 A 剧情 → B 重来（Take two）→ C 商品写实 → CTA（引导关注主页，不说品牌名）→ 尾板（最好不要，要留只闪一下）。样板 P04（CTA 和尾板按第二节新做法改）。

## 七、发布前检查（NRT 专属）

- [ ] 画面、口播、字幕里没有网址；CTA 没说品牌名
- [ ] 出镜商品都在官网目录里，规格数字与官网一致
- [ ] 品牌名念法人耳确认过：听起来是 "nature restaurant"
- [ ] logo 拼写放大核对过
