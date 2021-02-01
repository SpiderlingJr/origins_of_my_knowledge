## pandas DataFrame Plots
### DataFrame.plot


Ein kleiner Überblick über die von pandas DataFrames eigens implementierten Plotmöglichkeiten. Diese sind in der Regel denen von matplotlib und seaborn vorzuziehen, da sie ohnehin schon auf der vorliegenden Datenstruktur operieren und sehr einfach zu verwenden sind. Im Hintergrund benutzen Sie soweit ich weiß ohnehin matplotlib.

https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html

**Beispiel**:
```
from pandas import DataFrame

df = DataFrame([[4,3,2,1], [3,4,5,6]])
df.plot.bar()

```


**Plots**
- Basic: df.plot() (Besonders für Zeitreihen interessant)
- bar
- hist
- box
- kde / density
- scatter
- hexbin
- pie

### DataDrame.plotting

**Beispiel**
```
from pandas.plotting import andrews_curves
data = pd.read_csv("data/iris.data")

plt.figure()
andrews_cureves(data, "Name")

```
**Plots**
- scatter_matrix
- andrews_curves
- lag_plot
- autocorrelation_plot (https://en.wikipedia.org/wiki/Correlogram)
- radviz


# seaborn
