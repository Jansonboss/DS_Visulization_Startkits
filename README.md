# Visulization Template (Matplotlib, ggplot2)

```

# maplotlib
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
%config InlineBackend.figure_format = 'retina'

fig, axes = plt.subplots(nrows=3, ncols=2, figsize=(6,6))  # make one subplot (ax) on the figure
axes = axes.flatten() # it comes out as a 2D matrix; convert to a vector

axes[0].hist(df_cars['WGT'])
axes[1].plot(cyl, avg_mpg)
axes[2].scatter(df_cars['WGT'], df_cars['MPG'])
axes[3].plot(avg_mpg_per_wgt)
axes[4].bar(cyl, avg_mpg)
axes[5].boxplot([cyl4,cyl6,cyl8])

plt.tight_layout() # I add this anytime I have a grid as it "does the right thing"
plt.show()




# ggplot2 in python
from plotnine.data import economics
from plotnine import ggplot, aes, geom_line

(
    ggplot(economics)  # What data to use
    + aes(x="date", y="pop")  # What variable to use
    + geom_line()  # Geometric object to use for drawing
)
```


Useful Resources:

*Matplotlib library*

- Basic plot: https://github.com/parrt/msds593/blob/master/notebooks/matplotlib-cookbook.ipynb
- Beautify plot: https://github.com/parrt/msds593/blob/master/notebooks/matplotlib-beautify.ipynb
- Customize plot: https://github.com/parrt/msds593/blob/master/notebooks/matplotlib-customize.ipynb
- CV plot example: https://www.kaggle.com/eduardo4jesus/stanford-cars-dataset-a-quick-look-up