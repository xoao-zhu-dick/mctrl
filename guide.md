# mctrl使用教程
> ~~ngt似乎搞了个很有用的指令~~

## 目录
> ### 1. mctrl是什么
> ### 2. mctrl指令
> #### 2.1 mctrl指令中的名称
> #### 2.2 mctrl指令的使用方法

### 1. mctrl是什么
ModelCtrl

### 2. mctrl指令

在游戏内的指令为 `/mctrl`

#### 2.1 mctrl指令中的名称
名称 | 游戏内名称
:-- | :--
NOTCH | `notch`
DIR | `dir`
DATA_MAP | `dm:<data name>`
VEHICLE_STATE | `state:<data name>`
V_MOV_DIST | `move`
V_ADD_YAW | `addYaw`
V_ADD_PITCH | `addPitch`
FIRE | `fire`

#### 2.2 mctrl指令的使用方法

- 注意 **输错数值是否崩溃**
- 指令有风险，出事自己处理（跑

游戏内名称 | 游戏内指令 | 作用 | 输错数值是否崩溃
:-- | :-- | :-- | :--
`notch` | `mctrl <train> notch <-8 ~ 5>` | 调整列车档位 | **是**
`dir` | `mctrl <train> dir <0 or 1>` | 调整列车行驶方向 0正 1反 | **是**
`dm:<data name>` | `mctrl <?> dm:<data name> <(type)value>` | 调整 DataMap | 否
`state:<data name>` | `mctrl <vehicle> state:<data name> <value>` | 暂不清楚 | 暂不清楚
`move` | `mctrl <vehicle> move <distance>` | 移动载具 | 暂不清楚
`addYaw` | `mctrl <vehicle or artillery> addYaw <value>` | 调整载具或大炮 | 否
`addPitch` | `mctrl <artillery> addPitch <value>` | 调整载具或大炮 | 否
`fire` | `mctrl <artillery> fire <number of bullet>` | 大炮发♂射 | 否
