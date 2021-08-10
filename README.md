# Visulization Startkits (Matplotlib, ggplot2)


`Matplotlib`
```
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

# Decoration
plt.xlabel("Taxis Duration in Seconds")
plt.ylabel("index")


#Decoration
plt.xticks(rotation='70')
ax.set_yticks([0, 5, 10, 15, 20, 25, 30])
ax.set_yticklabels(["0%","5%", "10%", "15%", "20%", "25%", "30%"])


#lightening the borderbound
ax.spines["top"].set_alpha(.0)
ax.spines["right"].set_alpha(.0)
ax.spines["left"].set_alpha(.0)
ax.spines["bottom"].set_bounds(0, 59)
ax.spines["bottom"].set_linewidth(0.6)

#add arrow
ax.annotate("", xy=(50, 5), # start point position
            xytext=(10, 30), # arrow head position
           arrowprops=dict(arrowstyle="->"))

ax.set_xlabel("Cylinders")
ax.set_ylabel("MPG")

plt.xticks(rotation='70') # rotate x ticks label
plt.axis('off')

plt.xlabel("Taxis Duration in Seconds")
plt.ylabel("index")

plt.show()
```




`ggplot2`
```
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