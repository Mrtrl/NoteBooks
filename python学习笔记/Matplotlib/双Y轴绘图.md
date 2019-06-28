## 双Y轴绘图

### Twinx

```python
# encoding:utf-8
import numpy as np
import matplotlib.pyplot as plt
from matplotlib import mlp
mlp('mathtext', default='regular')

time = np.arange(10)
temp = np.random.random(10)*30
Swdown = np.random.random(10)*100 - 10
Rn = np.random.random(10)*100 -10

fig = plt.figure()
ax = fig.add_subplot(111)
ax.plot(time, Swdown, '-', label = 'Swdown')
ax.plot(time, Rn, '-', label = 'temp')
ax.legend(loc=0)
ax.grid()
```

