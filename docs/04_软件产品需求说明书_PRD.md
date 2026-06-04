# 软件产品需求说明书 PRD v0.1

## 产品目标

建设一套覆盖后台、设备端、菜谱编辑端、日志分析端和规则引擎的安全治理系统。

## 需求模块

1. 菜谱动作链解析模块
2. 执行日志与视频时间对齐模块
3. 危险规则引擎模块
4. 菜谱风险评分模块
5. 投油 / 投主料风险识别模块
6. 累计能量计算模块
7. 温度数据标准化模块
8. 控制功率 / 实际功率曲线记录模块
9. 安全基准曲线管理模块
10. 录菜端安全校验模块
11. 客户端安全交互与灰度策略模块
12. 后台风险看板与人工复核模块

## 核心公式

```text
oil_to_food_interval = first_main_ingredient_time - oil_added_time
E = Σ(P_i × Δt_i)
E_effective = Σ(P_i × Δt_i × η_i)
RiskScore = Σ(W_i × Factor_i)
```

## 功率优先级

1. actual_power：机芯实际输出功率
2. control_power：下位机收到的控制功率
3. set_power：上位机 / 菜谱设定功率

复刻时优先复刻 control_power_curve，actual_power_curve 用于校验。
