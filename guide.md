# mctrl使用教程
> ~~ngt似乎搞了个很有用的指令~~

## 目录
> [1. mctrl是什么](#1-mctrl是什么)  


### 1. mctrl是什么
全名 `ModelCtrl`，可用来控制实体

### 2. mctrl指令

`/mctrl <target> <category> <value>`  
目标：`@a` 全部，`@n` 最近，`@r:00` 范围，或者是实体名 (默认 `no_name`)

#### 2.1 mctrl指令的使用方法

- 注意 **输错数值是否崩溃**
- 指令有风险，出事自己处理（跑

名称 | 指令 | 作用 | 输错数值是否崩溃
:-- | :-- | :-- | :--
`notch` | `mctrl <train> notch <-8 ~ 5>` | 调整列车档位 | **是**
`dir` | `mctrl <train> dir <0 or 1>` | 调整列车行驶方向。`0` 正，`1` 反 | **是**
`dm:<data name>` | `mctrl <?> dm:<data name> <(type)value>` | 调整 DataMap | 否
`state:<data name>` | `mctrl <vehicle> state:<data name> <value>` | 暂不清楚 | 暂不清楚
`move` | `mctrl <vehicle> move <distance>` | 移动载具 | 暂不清楚
`addYaw` | `mctrl <vehicle or artillery> addYaw <value>` | 调整载具或大炮 | 否
`addPitch` | `mctrl <artillery> addPitch <value>` | 调整载具或大炮 | 否
`fire` | `mctrl <artillery> fire <number of bullet>` | 大炮发♂射 | 否

举例：比如想设置一辆名为 `test` 列车的档位为 `3`，那么输入 `mctrl test notch 3` 即可

#### 2.2 DataMap 扩展

每个实体都有 DataMap 数据，可以调整 DataMap 数据来控制组件

- DataMap 数据名称大小写需保持一致

这里以列车为例

- `Notch` 和 `Direction` 可以用 `mctrl <train> <notch or dir> <value>` 替代

DataMap 数据名称 | 中文名称 | 类型 | 数值 | 备注
:-- | :-- | :-- | :-- | :--
`Role` | 列车位置 | `Int` | `0` 前，`1` 中，`2` 后 | 无
`Destination` | 终点站 | `Int` | 第一个是 `0`，以此类推 | 无
`Announcement` | 车内广播 | `Int` | 第一个是 `0`，以此类推 | 只能调整，不能播放
`Light` | 车灯 | `Int` | `0` 关，`1` 开前灯，`2` 开前灯尾灯 | 无
`Pantograph` | 受电弓 | `Int` | `0` 降，`1` 升 | 无
`Notch` | 档位 | `Int` | `-8 ~ 5` | **输错数值崩溃**
`InteriorLight` | 车内灯 | `Int` | `0` 关，`1` 开，`2` 彩灯 | 无
`Direction` | 方向 | `Int` | `0` 正，`1` 反 | 只能调整座位方向 (bug)，**输错数值崩溃**
`ChunkLoader` | 区块加载器 | `Int` | `0 ~ 8` | 无
`Door` | 车门 | `Int` | `0` 全关，`1` 开一侧，`2` 开一侧，`3` 全开 | 无

举例：比如想设置一辆名为 `test2` 列车的车门为全开，那么输入 `mctrl test2 dm:Door (Int)3`即可
