---
title: "Matplotlib展示中文"
weight: 2
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

在[**Matplotlib**](https://matplotlib.org/)中展示中文，防止乱码

核心代码：

```python
plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
plt.rcParams['axes.unicode_minus'] = False #用来正常显示负号
```

完整代码：

```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import Lasso

plt.rcParams['font.sans-serif']=['SimHei'] #用来正常显示中文标签
plt.rcParams['axes.unicode_minus'] = False #用来正常显示负号

# 生成模拟数据
np.random.seed(42)
disciple_count = np.random.randint(50, 200, size=20)
establishment_years = np.random.randint(1, 100, size=20)
weapon_types = np.random.randint(1, 10, size=20)
master_skill = 2 * disciple_count + 1.5 * establishment_years + 3 * weapon_types + np.random.randn(20) * 20 + 100

# 数据转换为二维数组
X = np.column_stack((disciple_count, establishment_years, weapon_types))
y = master_skill

# 创建Lasso回归模型并训练
lasso_reg = Lasso(alpha=0.1)
lasso_reg.fit(X, y)

# 打印模型参数
print("截距:", lasso_reg.intercept_)
print("系数:", lasso_reg.coef_)

# 可视化回归平面（这里只能展示两个特征的二维平面图）
plt.scatter(disciple_count, master_skill, color='blue', label='实际数据')
plt.plot(disciple_count, lasso_reg.intercept_ + lasso_reg.coef_[0] * disciple_count + lasso_reg.coef_[1] * np.mean(establishment_years), color='red', linewidth=2, label='回归直线')
plt.title("武侠小说中的Lasso回归示例")
plt.xlabel("弟子数量")
plt.ylabel("掌门武功修为")
plt.legend()
plt.show()
```

