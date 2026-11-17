# Shoe Ground Fix v2.2.0

Project Zomboid 42.21 模组，为 Frockin Splendor! Vol.3 / Vol.5 的 16 个鞋类 `clothingItem` 类型应用垂直抬升着色器，修复可变身形环境下鞋底陷地。

## 当前内容

- 覆盖 **16 款**：Vol.5 的 9 款与 Vol.3 的 7 款。每款对应一份 XML 覆盖文件，因此当前共 **16 个 XML**。
- **15 款抬升 30 mm**；`KIU_THBoots` 抬升 **40 mm**。
- 共有 **2 个着色器变体、6 个着色器文件**。动态顶点着色器基于游戏 42.21 的 `basicEffect.vert`，只增加一条 Y 轴偏移；片段着色器与静态顶点着色器逐字节保持游戏原版内容（忽略换行格式差异）。
- 没有网格 FBX 覆盖文件。当前版本通过 XML 着色器引用和顶点着色器实现抬升。

30 mm 按 `30 / 1000 / 1.5` 换算为模型单位 `0.020000`；40 mm 换算为 `0.026667`。所有 XML 保留来源文件内容，只增加对应的 `<m_Shader>` 引用。

## 覆盖名单

**Vol.5（9 款）**：`FF_Boots_HF_New`、`FF_Boots_HF_New_Long`、`FF_Boots_HF_New_Longer`、`FF_Boots_HF_New_Longest`、`FF_Boots_HighHeels`、`FF_Boots_UGG_DwarfHeel`、`FF_Boots_UGG_Heel`、`FF_Boots_UGG_KneehighHeel`、`FF_Boots_UGG_ThighhighHeel`。

**Vol.3（7 款）**：`KIU_Heels`、`KIU_Heels_High`、`KIU_Heels_Low`、`KIU_Boots`、`KIU_LongBoots`、`KIU_THBoots`、`KIUx_Woman_Shoe`。

其中只有 `KIU_THBoots` 使用 40 mm 着色器；名单中的其余 15 款使用 30 mm 着色器。

## 来源与安装

仓库包含可加载的着色器及 XML 覆盖文件；XML 来源于 Frockin Splendor! Vol.3 / Vol.5，着色器基于游戏 42.21 的基础着色器。将仓库内容放入 `Zomboid/mods/ShoeGroundFix/` 并启用本模组。

模组加载顺序应排在 Frockin Splendor! Vol.3 / Vol.5 之后，使同名 XML 覆盖生效。

## 数量与历史证据

当前 v2.2.0 的口径是 **16 个 clothingItem 类型、16 个 XML、2 个着色器变体、6 个着色器文件、0 个网格 FBX 覆盖**。旧的“12 个 XML / 17 个网格”来自此前静态网格抬升版本，不能代表当前 v2.2.0 输出。

静态验证确认 16 份 XML 的语法与来源差异、两个着色器变体的偏移量、游戏基础着色器保持情况和版本字段。**着色器在游戏内的实际显示效果尚未验证**；需在真实客户端确认鞋底高度、着地表现和模型是否正常渲染。
